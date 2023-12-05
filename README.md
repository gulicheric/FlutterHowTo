# How To Learn Flutter

## 1. Prerequisites 

This might seem like an easy step, but it's not. It might even take a few days to fully set up everything. 

#### Follow everything from here to install
https://docs.flutter.dev/get-started/install

#### Note

Errors will pop up, even when you are following all the instructions. Don't panic. Just copy the error message onto google, and eventually the issues will go away.

If you run flutter doctor in your command line and you see that everything is checked, you are good to go.

### Simulator

For Mac, you need to have the Simulator app. The flutter docs will show you how to do that when you are installing everything.

## How to learn?

Creat a project! 

The best way of learning is by doing. Do NOT do something that you found on YouTube. You should do something that is new, so that you will have to implement everything yourself. 

#### Note

The most important thing for you in this step is NOT use chatGTP for any code. You can ask it questions as to why your code isn't working, but in your prompt, do not ask for a working solution, because this will inhibit your learning. Again, the whole point of the exercise is to learn. Once you understand how things work, you can then use ChatGPT to you advantage. 


## Most Important Parts

* Widgets

  Widgets are the building blocks of flutter. Everything is a wiget. You want to write text? Use the text widget. You want to create an App Bar? Use the appBar widget. Every widget has properties and are very similar to objects in java.

  For example:

    This is part of the Text Widget
   ```
  class Text extends StatelessWidget {
        const Text(
            String this.data, {
            this.style,
        })
  } 
  ```
  and you can make the following from it: 

    `Text("Hello", TextStyle(color: Colors.red))`

    The screen will display Hello in red.

    This is very similar to Java class 

    ```
    class Text {
        private String data;
        private TextStyle style;

        public Text(data, style) {
            this.data = data;
            this.style = style
        }
    }
    ``` 

    Widgets are basically classes


* State 

    This is the second most important concept to understand.

    First, just use Stateful Widget, and use the concept of setState(), since you will starting with an easy project. However, then you should learn how to use Riverpod 2.0 as make your project harder

* Navigation

    Learning how to use Navigation is very difficult. You should learn how to use go_router

* Futures

    You need to understand that when you deal with data that you are accessing from online, it will take some time to retrieve the information. Hopefully it will be done in milliseconds, but it could take a few seconds. This is where the concept of futures is really important. You will have to understand this.


These are the 4 most important part of Flutter, from what I know.

## Packages

Flutter has packages, which are just widgets already made for you. Anyone can make them. Even you! Some example of packages that have been created are shimmer (which makes the loading screen shimmer), video_player (allows you to display video on your app), and riverpod(state management). There are over 20,000 packages created. Some are needed, while others are nice to have if you don't want to make it yourself.

Here the website. 

https://pub.dev/packages?sort=popularity

Every package has an example. You should be familiar with being able to download the package, and test it out with there example. It is not something you NEED to do, however, it makes it a lot easier to implement if your code, when you can run the exmaple on your computer and see what the package does.

## Database

I would recommend you use Firebase, since Firebase and Flutter are both made by google, they make it really easy to use.

## How to structure your app.

You should structure your app by feature

If you are doing an app like Instagram, you should have different folders for homepage, profile, and notifications.

The structure of each folder should be as follows:

1. Screen - what is actually being displayed on screen
2. Util - where you get your data from firebase
3. Model - Objects you create. 

For example, if you want to implement a profile page.

Model will be ProfileModel that is a class 

```
class ProfileModel {
    final String username;
    final String picture;
    final String posts;
}
```

Then in your util page, you get the data

```
class ProfileUtil {
    static Futre<ProfileModel> getProfileData() {
        var result = FirebaseFirestore.instace.get("Users").doc(user).get()
        return result.data().forEach(
            'username': username;
            'picture': picture;
            'posts': posts;
        );
    }
}
```

In your screen you display the data.

```
Text(getProfileData.username)
```

### YouTubers To Learn From

1. https://www.youtube.com/@HeyFlutter

He is by far the best one. He has someone else do his videos now and they are not as good, but his old videos are amazing.

That's pretty much it lol. If you are stuck and want to learn how to do something, just type it in on youtube to see a tutorial. Hopefully the guy above made one, but there are plenty of other people out there. 

## Last Thing

You might ask yourself - I don't know what widgets are out there, what each of them does, or how you're supposed to know everything!

You're not supposed to know everything. Just take it day by day, and eventually you will get familiar with everything. 
