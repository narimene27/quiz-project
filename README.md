# quiz-project
package com.example.myapplication
//créer une classe AppQuiz qui comme arguments question et reponses de plus le resultat
class AppQuiz(var question:string , var reponse1:string,var reponse2:string, var resultat:int) {
    //créer une methode pour valider ou pas la reponse de l'utilisateur
    fun isCorrect(reponseUtilisateur:int ):Boolean {
        if(reponseUtilisateur == resultat)
            return true

            return false
    }
}
package com.example.myapplication

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle

class MainActivity1 : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main1)
    }

    fun onClickjouer(view:View){
        //créer un intent et l'avoir en argument
        val Intent = intent(packagecontext this, MainActivityquiz::class.java)
        startActivity(intent)

    }

package com.example.myapplication

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle

class MainActivityquiz : AppCompatActivity() {

    var AllQuiz = ArrayList<AppQuiz>{}
//créer une variable qui permet de definir le nombre de bonnes reponse et de parcourir les questions
    var resultatCorrect :int = 0
    var currentcmpt:int = 0

//création du quiz
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_mainquiz)

        AllQuiz.add(AppQuiz) { question:"c'est quoi le volleyball?", reponse1:"un plat", reponse2:"un sport", resultat:2 }
        AllQuiz.add(AppQuiz) { question:"De combien de joueurs se compose une équipe de volleyball", reponse1:"sept", reponse2:"douze", resultat:2 }
        AllQuiz.add(AppQuiz) { question:"y a combien de types de rotations", reponse1:"quatre", reponse2:"plusieurs", resultat:1 }
        AllQuiz.add(AppQuiz) { question:"comment s'appelle l'entraineur de l'equipe nationale de France du volley", reponse1:"domonique baeyens", reponse2:"laurent tillie", resultat:2 }
        AllQuiz.add(AppQuiz) { question:"face a qui la france a eté disqualifié en 2018 au volleyball", reponse1:"serbie", reponse2:"chine", resultat:1 }
        AllQuiz.add(AppQuiz) { question:"quel poste occupe le chargé de receptionner la balle au volley", reponse1:"libero", reponse2:"passeur", resultat:1 }

        affichequestion(allQuiz.get(resultatCorrect))
    }

    // créer une fonction qui affiche et lance le quiz
    fun affichequestion(allQuiz:AppQuiz){
        //recuperer les questions et reponses
        txtQuestion.setText(AppQuiz.question)
        reponse1.setText(AppQuiz.reponse1)
        reponse2.setText(AppQuiz.reponse2)
    }
    fun onClickreponse(view:View) {
        val AppQuiz = allQuiz.get(resultatCorrect)
        if (AppQuiz isCorrect (reponseresultat)) {
            resultatCorrect = resultatCorrect + 1
        } else {
            resultatCorrect = resultatCorrect
        }
        //succession de questions
        currentcmpt +1
        //execution de la fin du quiz laisser un message
        if (currentcmpt  > 7){
            var alert = alertDialog.Builder(context this)
            alert.setmessage("fin du quiz")
            alert.setmessageB("votre score est : + resultatCorrect+ ")
        }
        else{
            currentindex+1
        }
    }

}
