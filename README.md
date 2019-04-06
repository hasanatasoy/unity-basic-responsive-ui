```sh
public class ScreenResolutionService
{
    public void setScreenConfiguration(ref float height, ref float width)
    {
        float resolutionFactor = (float)Screen.width / (float)Screen.height;
        height = 2 * Camera.main.orthographicSize;
        width = resolutionFactor * height;
    }
}
```

```sh
public class GameLogic : MonoBehaviour
{
    
    public float height;
    public float width;
    public ScreenResolutionService screenResolutionService = new ScreenResolutionService();
    
    void Start()
        {
            screenResolutionService.setScreenConfiguration(ref height, ref width);
            anyGameObject.transform.localScale += new Vector2(width/2 , height/2);
        }

        void Update()
        {
       
        }
}
```
