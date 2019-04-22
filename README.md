# wethCast

You can download this file and run in your browser directly.

What this file consist of?

- HTML
- JavaScript
- AJAX

# Feature!

- Fetch weather information according to user input using [OpenWeatherMap API](https://openweathermap.org/api) .

You can also:

- Clone or Download ZIP from GitHub
- Copy Raw and paste in your file.

Clone using command:

```
git clone https://github.com/malavvasita/wethCast.git
```

After cloning, just run the file in browser and open the inspector tool. You can see weather information in console according to values you have given.

### How it will work?

- First of all you have to create an account on [OpenWeatherMap](https://home.openweathermap.org/users/sign_up), because you will need an API key to make AJAX call.
- You can take your API key from [here](https://home.openweathermap.org/api_keys) after logging in.
- Paste that copied API key [#44](https://github.com/malavvasita/wethCast/blob/c70aaa7540ad752efa45c20af72f3d01291a6c02/index.html#L44)
- You are good to go now and run the weathCast.

`Note: Be careful while putting API key.`

# What else you can do?

Do you want to modify this and make things work according to your need? You can obviously do that by doing minor changes.
On line number [#39](https://github.com/malavvasita/wethCast/blob/c70aaa7540ad752efa45c20af72f3d01291a6c02/index.html#L39) I have defined constants that I can have information of.

> There are lot more options you can try with and input as arguments. Look for [Documentation](https://openweathermap.org/current#one) and add argunents as per your need.

# The block you need to understand for output:

After success AJAX call there is function `showDataInConsole` I have used. You can find function defination on line number [#25](https://github.com/malavvasita/wethCast/blob/c70aaa7540ad752efa45c20af72f3d01291a6c02/index.html#L25),

```
showDataInConsole(
    "./weather " +
    data.name +
    ", " +
    inputs["zip"] +
    "\n Temprature: " +
    data.main.temp +
    String.fromCharCode(176) +
    "c" +
    " | Date and Time in " +
    data.name +
    " is " +
    new Date(data.dt * 1000)
      .toISOString()
      .slice(0, 19)
      .replace("T", " ")
);
```

So how can you interprete the data that we have passed in function above.

- At first we will get `Data` on success AJAX call in JSON format. So we will get information from that data and show that in console.
- `data.name` : It is the name of City that user will input and we will search for.
- `inputs["zip"]` : Zip code of perticular place in city.
- `data.main.temp` : Temprature at place in city that user inputted.
- `String.fromCharCode(176)` : This has been used to show degree symbol in console.
- `new Date(data.dt * 1000) .toISOString() .slice(0, 19) .replace("T", " ")` : For displaying date and time, we have used this JS syntax.

Sample output for this in console will look something like:

```
./weather Ahmedabad, 380007
 Temprature: 41°c | Date and Time in Ahmedabad is 2019-04-21 10:00:00
```
