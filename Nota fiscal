def calcular_desconto(preco_total, cupom):
    desconto = 0
    if cupom == 10:
        desconto = preco_total * 0.10
    elif cupom == 20:
        desconto = preco_total * 0.20
    elif cupom == 30:
        desconto = preco_total * 0.30
    elif cupom == 40:
        desconto = preco_total * 0.40
    elif cupom == 50:
        desconto = preco_total * 0.50
    return desconto

cupons_disponiveis = [10, 20, 30, 40, 50]

def gerar_nota_fiscal(preco_total, cupom_utilizado):
    valor_desconto = calcular_desconto(preco_total, cupom_utilizado)
    preco_com_desconto = preco_total - valor_desconto

    nota_fiscal = f"""
    ------- Nota Fiscal -------
    Valor total da compra: R$ {preco_total:.2f}
    Cupom de desconto utilizado: {cupom_utilizado}%
    Valor do desconto: R$ {valor_desconto:.2f}
    Valor da compra com desconto: R$ {preco_com_desconto:.2f}
    ---------------------------
    """
    return nota_fiscal

def main():
    preco_total = float(input("Digite o valor total da compra: "))
    cupom_utilizado = int(input("Digite o cupom de desconto utilizado (10%, 20%, 30%, 40%, 50%): "))

    if cupom_utilizado in cupons_disponiveis:
        nota_fiscal = gerar_nota_fiscal(preco_total, cupom_utilizado)
        print(nota_fiscal)
    else:
        print("Cupom de desconto inválido. Por favor, escolha um cupom disponível.")

if __name__ == "__main__":
    main()
