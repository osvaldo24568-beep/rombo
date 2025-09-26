from abc import ABC, abstractmethod

class Figura(ABC):
    @abstractmethod
    def calcular_perimetro(self) -> float:
        pass

    @abstractmethod
    def calcular_area(self) -> float:
        pass

    @abstractmethod
    def obtener_nombre(self) -> str:
        pass

class Rombo(Figura):
    def __init__(self, diagonal_mayor: float, diagonal_menor: float, lado: float):
        self.diagonal_mayor = diagonal_mayor
        self.diagonal_menor = diagonal_menor
        self.lado = lado

    def calcular_perimetro(self) -> float:
        return 4 * self.lado

    def calcular_area(self) -> float:
        return (self.diagonal_mayor * self.diagonal_menor) / 2

    def obtener_nombre(self) -> str:
        return "Rombo"

if __name__ == "__main__":
    r = Rombo(6, 4, 5)
    print(r.obtener_nombre())
    print(f"Perímetro: {r.calcular_perimetro():.2f}")
    print(f"Área: {r.calcular_area():.2f}")
