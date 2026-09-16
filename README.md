# atividade-de-decolagem
# Relatório operacional de pré-decolagem

telemetria = {
    "temperatura_interna_c": 22.4,
    "temperatura_externa_c": 18.7,
    "integridade_estrutural": 1,
    "nivel_energia_pct": 86,
    "pressao_tanques_kpa": 310,
    "modulos_criticos": "OK"
}

def verificar_pre_decolagem(dados):
    verificacoes = {
        "Temperatura interna":
            18 <= dados["temperatura_interna_c"] <= 27,

        "Temperatura externa":
            -20 <= dados["temperatura_externa_c"] <= 45,

        "Integridade estrutural":
            dados["integridade_estrutural"] == 1,

        "Nível de energia":
            dados["nivel_energia_pct"] >= 70,

        "Pressão dos tanques":
            280 <= dados["pressao_tanques_kpa"] <= 340,

        "Módulos críticos":
            dados["modulos_criticos"].upper() == "OK"
    }

    for item, aprovado in verificacoes.items():
        print(f"{item}: {'OK' if aprovado else 'FALHA'}")

    if all(verificacoes.values()):
        resultado = "PRONTO PARA DECOLAR"
    else:
        resultado = "DECOLAGEM ABORTADA"

    print("\nRESULTADO:", resultado)

    return resultado, verificacoes


def analisar_energia(
    capacidade_kwh,
    carga_pct,
    consumo_decolagem_kwh,
    perdas_pct,
    consumo_cruzeiro_kwh_h=100
):
    energia_inicial = capacidade_kwh * (carga_pct / 100)

    perdas = energia_inicial * (perdas_pct / 100)

    energia_util = energia_inicial - perdas

    restante = energia_util - consumo_decolagem_kwh

    autonomia_h = restante / consumo_cruzeiro_kwh_h

    print(f"Energia armazenada: {energia_inicial:.1f} kWh")
    print(f"Perdas estimadas: {perdas:.1f} kWh")
    print(f"Energia após a decolagem: {restante:.1f} kWh")
    print(f"Autonomia estimada: {autonomia_h:.2f} horas")

    return restante, autonomia_h


# Executando a verificação
resultado, verificacoes = verificar_pre_decolagem(telemetria)

print("\n--- ANÁLISE ENERGÉTICA ---")

energia_restante, autonomia = analisar_energia(
    capacidade_kwh=1200,
    carga_pct=86,
    consumo_decolagem_kwh=180,
    perdas_pct=5
)
