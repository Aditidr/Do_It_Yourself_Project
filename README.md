# Do_It_Yourself_Project

Project Code:
package com.aditi.birthdaygreeting

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.TextView
import kotlinx.android.synthetic.main.activity_birthday_wishing.*

class BirthdayWishingActivity : AppCompatActivity() {

    companion object {
        const val  NAME_EXTRA = "name_extra"
    }
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_birthday_wishing)

        val name = intent.getStringExtra(NAME_EXTRA)
        birthdayGreeting.text = "Happy Birthday\n   $name!"





    }
}

package com.aditi.birthdaygreeting

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.view.View
import android.widget.EditText
import android.widget.Toast

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }

    fun createBirthdayCard(view: View) {

        val userInput: EditText=findViewById(R.id.userInput)
        val name = userInput.text.toString()

        val intent = Intent(this, BirthdayWishingActivity::class.java)

        intent.putExtra(BirthdayWishingActivity.NAME_EXTRA, name)
        startActivity(intent)
    }
}

https://user-images.githubusercontent.com/96663731/147406241-99a1df80-e0e3-43de-890e-7bbb9a4e2546.MP4

