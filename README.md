# Minliezra
Hbd cepir

import turtle
import time

# Fungsi untuk menggambar kue ulang tahun
def gambar_kue():
    t = turtle.Turtle()
    t.speed(2)

    # Menggambar dasar kue
    t.penup()
    t.goto(-100, -150)
    t.pendown()
    t.color("chocolate")
    t.begin_fill()
    for _ in range(2):
        t.forward(200)
        t.left(90)
        t.forward(50)
        t.left(90)
    t.end_fill()

    # Menggambar lapisan tengah kue
    t.penup()
    t.goto(-75, -100)
    t.pendown()
    t.color("sandybrown")
    t.begin_fill()
    for _ in range(2):
        t.forward(150)
        t.left(90)
        t.forward(50)
        t.left(90)
    t.end_fill()

    # Menggambar lapisan atas kue
    t.penup()
    t.goto(-50, -50)
    t.pendown()
    t.color("peru")
    t.begin_fill()
    for _ in range(2):
        t.forward(100)
        t.left(90)
        t.forward(50)
        t.left(90)
    t.end_fill()

    # Menggambar lilin
    t.penup()
    t.goto(0, 0)
    t.pendown()
    t.color("red")
    t.begin_fill()
    t.forward(5)
    t.left(90)
    t.forward(20)
    t.left(90)
    t.forward(5)
    t.left(90)
    t.forward(20)
    t.left(90)
    t.end_fill()

    # Menggambar api lilin
    t.penup()
    t.goto(2.5, 20)
    t.pendown()
    t.color("yellow")
    t.begin_fill()
    t.circle(5)
    t.end_fill()

    t.hideturtle()

# Fungsi untuk menampilkan ucapan satu per satu
def tampilkan_ucapan():
    pen = turtle.Turtle()
    pen.hideturtle()
    pen.penup()
    pen.color("blue")
    pen.speed(0)

    # Menampilkan ucapan per huruf
    ucapan = "Selamat Ulang Tahun ce"
    pen.goto(0, -200)
    for i in range(len(ucapan)):
        pen.clear()
        pen.write(ucapan[:i+1], align="center", font=("Arial", 16, "bold"))
        time.sleep(0.2)

    # Kalimat tambahan (per kata)
    kalimat_list = [
        ("Safira ameliana putri", "white"),
        ("semoga sehat selalu", "green"),
        ("kalo ade sakit", "red"),
        ("baik tu mental, fisik, pikiran", "red"),
        ("atau mungkin perasaan", "red"),
        ("semoga cepet sembuh", "yellow"),
        ("Semoga ace menjadi", "white"),
        ("pribadi yang lebih dewasa", "green"),
        ("dan ape yang nek", "white"),
        ("ace capai semoga tercapai", "blue"),
        ("lah tu bai", "white"),
        ("( •-•)", "yellow")
    ]

    y_position = -230
    for kalimat, warna in kalimat_list:
        pen.goto(0, y_position)
        pen.color(warna)
        words = kalimat.split()
        for i in range(len(words)):
            pen.clear()
            pen.write(' '.join(words[:i+1]), align="center", font=("Arial", 12, "italic"))
            time.sleep(0.6)
        y_position -= 30

# Fungsi utama
def main():
    screen = turtle.Screen()
    screen.bgcolor("black")
    screen.title("Kue Ulang Tahun")

    gambar_kue()
    tampilkan_ucapan()

    turtle.done()

# Menjalankan program
main()