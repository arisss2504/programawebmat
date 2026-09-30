import math
import streamlit as st

st.title("Calculadora Geométrica")

figura = st.selectbox(
    "Seleccione la figura:",
    ["Cuadrado", "Rectángulo", "Triángulo", "Círculo", "Paralelogramo"],
)

if figura == "Cuadrado":
    st.latex(r"Área = lado^2 \quad | \quad Perímetro = 4 \cdot lado")
    lado = st.number_input("Lado:", min_value=0.0, value=1.0)
    st.write(f"**Área:** {lado**2:.2f}")
    st.write(f"**Perímetro:** {4*lado:.2f}")

elif figura == "Rectángulo":
    st.latex(
        r"Área = base \cdot altura \quad | \quad Perímetro = 2 \cdot (base +"
        r" altura)"
    )
    b = st.number_input("Base:", min_value=0.0, value=1.0)
    h = st.number_input("Altura:", min_value=0.0, value=1.0)
    st.write(f"**Área:** {b*h:.2f}")
    st.write(f"**Perímetro:** {2*(b+h):.2f}")

elif figura == "Triángulo":
    st.latex(r"Área = \frac{base \cdot altura}{2} \quad | \quad Perímetro = a+b+c")
    b = st.number_input("Base:", min_value=0.0, value=1.0)
    h = st.number_input("Altura:", min_value=0.0, value=1.0)
    l1 = st.number_input("Lado 1:", min_value=0.0, value=1.0)
    l2 = st.number_input("Lado 2:", min_value=0.0, value=1.0)
    st.write(f"**Área:** {(b*h)/2:.2f}")
    st.write(f"**Perímetro:** {b+l1+l2:.2f}")

elif figura == "Círculo":
    st.latex(r"Área = \pi \cdot r^2 \quad | \quad Perímetro = 2 \cdot \pi \cdot r")
    r = st.number_input("Radio:", min_value=0.0, value=1.0)
    st.write(f"**Área:** {math.pi * (r**2):.2f}")
    st.write(f"**Perímetro:** {2 * math.pi * r:.2f}")

elif figura == "Paralelogramo":
    st.latex(
        r"Área = base \cdot altura \quad | \quad Perímetro = 2 \cdot (base +"
        r" lado)"
    )
    b = st.number_input("Base:", min_value=0.0, value=1.0)
    h = st.number_input("Altura:", min_value=0.0, value=1.0)
    l = st.number_input("Lado inclinado:", min_value=0.0, value=1.0)
    st.write(f"**Área:** {b*h:.2f}")
    st.write(f"**Perímetro:** {2*(b+l):.2f}")
