# Test
            public SpriteRenderer characterSpriteRenderer;
            public void ApplySkin2D(Sprite newSkinSprite)
            {
                characterSpriteRenderer.sprite = newSkinSprite;
            }
            public MeshFilter characterMeshFilter;
            public MeshRenderer characterMeshRenderer;
            public void ApplySkin3D(Mesh newSkinMesh, Material newSkinMaterial)
            {
                characterMeshFilter.mesh = newSkinMesh;
                characterMeshRenderer.material = newSkinMaterial;
            }
using UnityEngine;

// Define a ScriptableObject for skin data
[CreateAssetMenu(fileName = "NewSkin", menuName = "Game/Skin Data")]
public class SkinData : ScriptableObject
{
    public string skinName;
    public Sprite skinSprite; // For 2D games
    // public Mesh skinMesh; // For 3D games
    // public Material skinMaterial; // For 3D games
    public int price;
}

// Player script to handle applying skins
public class PlayerSkinManager : MonoBehaviour
{
    public SpriteRenderer playerSpriteRenderer; // Assign in Inspector

    public void ApplySkin(SkinData selectedSkin)
    {
        if (selectedSkin != null)
        {
            playerSpriteRenderer.sprite = selectedSkin.skinSprite;
            // For 3D:
            // GetComponent<MeshFilter>().mesh = selectedSkin.skinMesh;
            // GetComponent<MeshRenderer>().material = selectedSkin.skinMaterial;
        }
    }

    // Example of loading a saved skin on start
    void Start()
    {
        string savedSkinName = PlayerPrefs.GetString("SelectedSkin", "DefaultSkin"); // "DefaultSkin" is a placeholder
        // Find the corresponding SkinData and apply it
        // (This would require a way to look up SkinData by name, e.g., a list of all skins)
    }
}




