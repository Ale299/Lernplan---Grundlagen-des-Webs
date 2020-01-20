const PubSub = require('pubsub-js'),

      http = require('http'),

      express = require('express'),

      readline = require('readline');

      

const rl = readline.createInterface({

        input: process.stdin,

        output: process.stdout

      })

 

var app = express();

 

var server = http.createServer(app);

server.listen(8000);

 

var warten = 'ist in der Warteschlange. Bitte haben Sie noch etwas Geduld', 

    zubereitet = 'wird gerade zubereitet',

    geliefert = 'wird gerade geliefert';

 

var pizzaTopic = 'Meine Pizza'

 

var httpAusgabe = function (statusText, zeitangabe) {

    app.get('/pizza/:details/:status', (req, res) => {

        req.query

        res.send(`Die Pizza ` + statusText + `. Vorraussichtlich noch ca. ` + zeitangabe + ` Minuten.`)

    })

}

 

var mySubscriber = function (msg, data) {

    //console.log( msg, data );

};

 

var token = PubSub.subscribe(pizzaTopic, mySubscriber);

 



 

//PubSub.publish(pizzaTopic, httpAusgabe(warten, 30));
PubSub.publish(pizzaTopic, httpAusgabe(geliefert, 30));
