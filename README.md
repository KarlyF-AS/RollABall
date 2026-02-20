# Roll a Ball - tuto Unity
Para este juego siguiendo paso por paso las indicaciones del tutorial de unity, crearmos distintos elementos, como: 
- Scripts (codigo del júego)
- Materiales (definimos posiciones, colores y otros ascpectos físicos de los objetos 3D)
- Prefabs (carpeta creada especificamente para los cubos giratorios)
- TeshMesh (texto en la pantalla del jugador)
- Scenes (donde estamos creando nuesto mundo)

## _Scripts_:
Dentro de la carpeta scripts, como y habia mencionado antes, tenemos el funcionamiento/logica de nuestro roll a ball
- CameraController: para el posicionamiento de la cámara (la vista del jugador)
 ```bash
 public class CameraController : MonoBehaviour
{
    //Objeto jugador
    public GameObject player;
    private Vector3 offset; // para fijar la distancia de la camara y el jugador


    // Start is called before the first frame update
    void Start()
    {
        offset = transform.position - player.transform.position; //calculando distancia de inicio
    }

    // Update is called once per frame
    void LateUpdate() //se carga luego de que el jugador empiece a moverse
    {
        transform.position = player.transform.position + offset;
    }
}
```
- PlayerController:
