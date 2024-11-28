# minimum-oklid-mesafesinin-hesaplanmas-
import math

# 1. Noktaların Tanımlanması
points = [(2, 3), (5, 1), (1, 4), (3, 7), (0, 0)]

# 2. Öklid Mesafesi İçin Fonksiyon Tanımlama
def euclideanDistance(point1, point2):
    """
    İki nokta arasındaki Öklid mesafesini hesaplar.
    """
    return math.sqrt((point2[0] - point1[0])**2 + (point2[1] - point1[1])**2)

# 3. Mesafelerin Hesaplanması
distances = []
for i in range(len(points)):
    for j in range(i + 1, len(points)):
        distance = euclideanDistance(points[i], points[j])
        distances.append((distance, points[i], points[j]))

# 4. Minimum Mesafenin Bulunması
min_distance, point1, point2 = min(distances, key=lambda x: x[0])

# Sonuçların Yazdırılması
print(f"Minimum Öklid Mesafesi: {min_distance:.2f}")
print(f"En Yakın Noktalar: {point1} ve {point2}")
