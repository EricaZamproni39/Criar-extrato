# Criar-extrato
supermarket-purchase-statement.
class ItemCompra:
    def __init__(self, nome, quantidade, preco_unitario):
        self.nome = nome
        self.quantidade = quantidade
        self.preco_unitario = preco_unitario

    def custo_total(self):
        return self.quantidade * self.preco_unitario

class ExtratoSupermercado:
    def __init__(self):
        self.itens = []

    def adicionar_item(self, item):
        self.itens.append(item)

    def gerar_extrato(self):
        print("Extrato de Compras no Supermercado")
        print("-" * 40)
        total = 0
        for item in self.itens:
            custo = item.custo_total()
            total += custo
            print(f"{item.nome:<20} {item.quantidade} x {item.preco_unitario:.2f} = {custo:.2f}")
        print("-" * 40)
        print(f"Total a pagar: {total:.2f}")

# Exemplo de uso
extrato = ExtratoSupermercado()
extrato.adicionar_item(ItemCompra("Arroz", 2, 5.50))
extrato.adicionar_item(ItemCompra("Feijão", 1, 4.75))
extrato.adicionar_item(ItemCompra("Macarrão", 3, 3.25))
extrato.adicionar_item(ItemCompra("Leite", 4, 2.80))
extrato.gerar_extrato()
