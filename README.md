# C-script-of-basket-to-grab-the-egg-and-score-update
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;


public class bucket : MonoBehaviour
{
    public int score;
    public Text ScoreTxt;

    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (score >= 10)
            YouWin();
    }

    void YouWin()
    { ScoreTxt.text = "You Win!!";
        Time.timeScale = 0f;
    }

    void OnTriggerEnter2D(Collider2D other)
    {
        Destroy(other.gameObject);
        AddScore();
    }

    void AddScore()
    { score++;
        ScoreTxt.text = score.ToString();
    }
}
