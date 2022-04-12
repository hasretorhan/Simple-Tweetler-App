# Simple-Tweetler-App
Web Proje Değerlendirme Vize Ödevi
Soru : Aşağıdaki veri setine göre bir 3 kullanıcı girişi ve tweetleri olucak girilen kişinin değil de diğer iki kişinin tweetleri gösteren uygulamayı giriniz.
// Simple Twitter App
var users = [
    {
        username: "kaan",
        password: "1234",
        friends: ["nuri", "büşra"]
    },
    {
        username: "nuri",
        password: "7777",
        friends: ["nuri", "ali"]
    },
    {
        username: "büşra",
        password: "0000",
        friends: ["hasret", "sema"]
    }

];

var tweets = [
    {
        username: "kaan",
        tweet: "Havalarda çok sıcak!!!"
    },
    {
        username: "büşra",
        tweet: "macbook mu tövbe!!!"
    },
    {
        username: "nuri",
        tweet: "künefeeeee!!!!"
    }
];

/* Kullanıcı Girişi */
var userNamePrompt = prompt("Kullanıcı adınızı giriniz!");
var passwordPrompt = prompt("Şifrenizi giriniz!");

/* Kullanıcın girişin tespiti */
function isUserValid(user, pass) {
    for (var i = 0; i < users.length; i++) {
        if (user === users[i].username && pass === users[i].password) {
            return true;
        }
    }
    console.log("Kullanıcı adı veya şifre hatalı");
    return false;
}
/* girilen kullanıcının değil de arkadaşların tweetleri*/

function signIn(user, pass) {
    if (isUserValid(user, pass)) {
        for (var i = 0; i < tweets.length; i++) {
            if (tweets[i].username == user) {
                continue
            }
            else {
                console.log(tweets[i].username);
                console.log(tweets[i].tweet);
            }
        }
    }
    else {
        console.log("Hata!!!");
    }
}

signIn(userNamePrompt, passwordPrompt);

