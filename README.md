import time
import streamlit as st

# Configuración de la página
st.set_page_config(
    page_title="ArqAI - Diseño Arquitectónico Emocional", page_icon="🏠", layout="centered"
)

# Estilos visuales personalizados
st.markdown(
    """
    <style>
    .main-title { font-size: 28px; font-weight: bold; color: #2C3E50; text-align: center; }
    .subtitle { font-size: 16px; color: #7F8C8D; text-align: center; margin-bottom: 30px; }
    .stButton>button { width: 100%; background-color: #2C3E50; color: white; font-weight: bold; border-radius: 8px; }
    .stButton>button:hover { background-color: #34495E; color: white; }
    </style>
""",
    unsafe_allow_html=True,
)

st.markdown(
    '<p class="main-title">🏠 ArqAI: Del Recuerdo al Espacio</p>',
    unsafe_allow_html=True,
)
st.markdown(
    '<p class="subtitle">Diseño arquitectónico basado en la memoria y las emociones del cliente</p>',
    unsafe_allow_html=True,
)

# Formulario con preguntas abiertas
with st.form("design_form"):
  st.subheader("Cuéntenos sobre usted y su visión")

  q1 = st.text_area(
      "1. ¿Tiene algún recuerdo muy presente de su infancia que le traiga paz"
      " o felicidad?"
  )
  q2 = st.text_area(
      "2. ¿Tiene algún sentimiento o emoción en particular que le transmita"
      " un lugar en particular?"
  )
  q3 = st.text_area(
      "3. ¿Con qué clima o tipo de entorno está más familiarizado y se siente"
      " más cómodo?"
  )
  q4 = st.text_area("4. ¿Tiene algún *hobby* o pasatiempo frecuente?")
  q5 = st.text_area("5. ¿Qué actividades realiza normalmente en su día a día?")
  q6 = st.text_area("6. ¿Para quién o quiénes está pensado este espacio?")
  q7 = st.text_area(
      "7. ¿Hay algún espacio que considere indispensable o de mayor"
      " importancia?"
  )

  submitted = st.form_submit_button("Generar Boceto y Render")

if submitted:
  if not q1 or not q6:
    st.warning(
        "Por favor, responda al menos las preguntas principales para poder"
        " iniciar el diseño."
    )
  else:
    with st.spinner(
        "Analizando respuestas y perfil emocional del cliente..."
    ):
      time.sleep(2)

    st.success("¡Análisis completado con éxito!")

    # Sección de Boceto Conceptual
    st.markdown("---")
    st.subheader("✏️ Paso 1: Boceto Conceptual Generado")
    st.write(
        "Basado en sus recuerdos de infancia, clima preferido y distribución de"
        " espacios indispensables:"
    )
    st.info(
        "[Simulación de Boceto Arquitectónico: Trazos preliminares en 2D,"
        " zonificación y ejes principales orientados a capturar la luz y la"
        " memoria expresada]."
    )

    with st.spinner("Generando render fotorrealista final..."):
      time.sleep(3)

    # Sección de Render Final
    st.markdown("---")
    st.subheader("✨ Paso 2: Render Fotorrealista Final")
    st.write(
        "Espacio arquitectónico materializado integrando sus emociones,"
        " actividades diarias y necesidades:"
    )
    st.success(
        "Renderizado 3D completado. Estilo: Arquitectura contemporánea con"
        " iluminación natural optimizada según sus preferencias climáticas y"
        " zonas de confort."
    )
    

