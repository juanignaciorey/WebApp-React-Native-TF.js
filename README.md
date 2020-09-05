# WebApp React-Native TF.js

_Se pide crear una aplicación web progresiva para plataformas móviles que permite a los usuarios(en general médicos clinicos) para clasificar imágenes de radiografias(sobre pneumonia) seleccionadas localmente o tomadas con la cámara de su dispositivo móvil. La aplicación debe permitir a los usuarios ejecutar un modelo sin conexión en áreas donde la conectividad a Internet puede ser escasa o inexistente._

### **TLDR**
_Es una WebApp en React-Native con un modelo en tensorflow. Se usara para la detección de pseumonia en imagenes de radiografia. Se usa un modelo de ML para evaluar las radiografias y devolver una respuesta_

_Consta de dos partes. Un API Rest Nodejs para ejecutar el modelo, y un front-end React-Native_

*Read this in other languages: [English](README.md), [Español](README.es.md), [한국어](README.ko.md), [日本語](README.ja.md), [简体中文](README.zh-cn.md), [正體中文](README.zh-tw.md).*

## Con esta solución: 
- Los datos permanecen en el dispositivo y la clasificación se realiza localmente
- La aplicación puede ejecutarse en computadoras de escritorio e "instalarse" en dispositivos móviles
- Los activos se almacenan en la memoria caché y el browser-storage

## Flujo

_Con TensorFlow.js, convertimos nuestros modelos de TensorFlow o Keras previamente entrenados en JavaScript para que se ejecuten en el navegador a través de la aplicación. Luego, tenemos una aplicación multiplataforma donde los usuarios pueden clasificar imágenes seleccionadas localmente o tomadas con la cámara de su dispositivo móvil. La aplicación usa TensorFlow.js y un modelo previamente entrenado convertido al formato TensorFlow.js para proporcionar las capacidades de inferencia. Este modelo se guarda localmente en el navegador usando IndexedDB, y se usa un trabajador de servicio para proporcionar capacidades sin conexión._

![work flow](https://d3bgxec5qvatpb.cloudfront.net/wp-content/uploads/2020/07/create-a-progressive-web-application-for-offline-image-classification-2048x1128.png)

1. Un modelo Keras/TensorFlow previamente entrenado se convierte al formato compatible con la web TensorFlow.js e integrado con la aplicación. Te interesa ver como ésta entrenado? [te paso el enlace a una PoC en Python y google Colab](https://)
2. El usuario inicia la aplicación web progresiva.
3. Se descargan las vistas al usuario, junto con los archivos de modelo TensorFlow.js.
4. Los activos y el modelo se almacenan localmente mediante el cache del navegador y el almacenamiento de IndexedDB.
5. El usuario toma una foto con una cámara de dispositivo o selecciona una imagen local.
6. La imagen se envía a través del modelo para la inferencia y se proporcionan las predicciones.
 
## Requerimientos

## Criterios de aceptación
- [ ] It must use semantic HTML
- [ ] It must use React
- [ ] It must be Responsive
- [ ] It must use CSS in JS
- [ ] It must have tests
  - [ ] Snapshot tests
  - [ ] Behavior tests
- [ ] It must use Reach Router
- [ ] It could use Reach UI components
- [ ] It must use Redux
- [ ] It must be a Progressive Web App
- [ ] It must pass with green the Performance tests of the Chrome Audits
- [ ] It must pass with green the Accessibility tests of the Chrome Audits
- [ ] It must pass with green the Best Practices tests of the Chrome Audits
- [ ] It must pass with green the SEO tests of the Chrome Audits
- [ ] It must pass with green the PWA tests of the Chrome Audits

## **Onboarding**
- [ ] El usuario debe tener una vista de inicio de sesión.
- [ ] Después de iniciar sesión, debería su componente camara.
- [ ] Le dara la opcion de elegir si quiere importar la foto o sacarla con la camara.
  - [ ] El usuario solo puede analizar una foto a la vez.
  - [ ] Mientras la analiza, debera ver una animación que compruebe la acción
- [ ] Una vez analizada la foto, el usuario tendra la opcion de compartir el resultado por whatsapp. Luego volvera a la pantalla anterior. 
  - [ ] En caso de compartirla debera haber un alert de confirmación 
