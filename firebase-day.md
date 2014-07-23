# Firebase Day

Today, we used [Firebase](https://firebase.com), a powerful data storage tool for your web applications. You should check out their [extensive and rapidly improving documentation](https://firebase.com/docs) to see how to use Firebase, or you can check out the several examples of real Firebase applications in production:
 - **Nest**, the programmable thermostat: [developer page](https://developer.nest.com/), and an [illustrative StackOverflow question](https://stackoverflow.com/questions/24611966/controlling-multiple-nest-thermostats-using-firebase)
 - **Other Firebase customers** like CBS, InstantCab, Instacart, and Citrix: [customers and case studies](https://www.firebase.com/customers/)
 - **The techlab website** stores all data and does all authentication through the Firebase API and the Firebase Simple Login API - [link](https://techlab.education)

## Compliment sharing

Remember how we built an incredibly cool app in less than an hour? Here's how we did it.

First, we laid out a very basic HTML page that contains an `h1` element, a `textarea` element, and a `button` element. We left out the styling so you could practice your CSS on this example. The CSS styles that I used in my example are [listed out below](#css-styles). If you copy and paste this example in, it should still work, it just won't look that good.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      /* Your styles for  the body, h1, textarea, and button go here */
      body { }
      h1 { }
      textarea { }
      button { }
    </style>
  </head>
  <body>
    <h1>Type in a compliment</h1>  
    <textarea></textarea>
    <button></button>
  </body>
</html>
```

## CSS styles

Here are my CSS styles from today, along with some comments (`/* .... */`) about what they do. If it isn't clear what a certain style does, try removing it and adding it to see how your page responds.

```css
body {
  background: #336699;  /* set the background to techlab blue */
  padding: 50px;        /* Make 50px of empty space around the edge of the window */
}
h1 {
  margin-top: 100px;    /* Push the h1 element and everything under it down 100px */
}
```







