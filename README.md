
1.Get all the countries from the Asia continent /region using the Filter function :

var request=new XMLHttpRequest();

request.open("GET","https://raw.githubusercontent.com/rvsp/restcountries-json-data/master/res-countries.json");
request.send();
request.onload=function(){
var result=JSON.parse(request.response);
console.log(result);

var res=result.filter((ele)=>ele.region==="Asia");
console.log(res);

}


2.Get all the countries with a population of less than 2 lakhs using Filter function :

var request=new XMLHttpRequest();
request.open("GET","https://raw.githubusercontent.com/rvsp/restcountries-json-data/master/res-countries.json");
request.send();
request.onload=function(){
    var result=JSON.parse(request.response);
    console.log(result);
for(var i=0;i<result.length;i++){
  var res=result.filter((ele)=>ele.population<200000);
  console.log(res);

}}

3.Print the following details name, capital, flag using forEach function :

var request=new XMLHttpRequest();
request.open("GET","https://raw.githubusercontent.com/rvsp/restcountries-json-data/master/res-countries.json");
request.send();
request.onload=function(){
    var result=JSON.parse(request.response);
    console.log(result);
    for(var i=0;i<result.length;i++){
    console.log(result[i].name);
    console.log(result[i].capital);
    console.log(result[i].flag);
}}


4.Print the total population of countries using reduce function

var request=new XMLHttpRequest();
request.open("GET","https://raw.githubusercontent.com/rvsp/restcountries-json-data/master/res-countries.json");
request.send();
request.onload=function (){
    var countryData=JSON.parse(this.response);
    const population=countryData.reduce((acc,element)=>{
        return acc+element.population;
    },0)
    console.log(population);
}

5.Print the country which uses US Dollars as currency

var request = new XMLHttpRequest();
request.open('Get', "https://raw.githubusercontent.com/rvsp/restcountries-json-data/master/res-countries.json")
request.send();
request.onload = function () {
        var data = JSON.parse(this.response);
        var cur=[];
        for(i=0;i<data.length;i++){
            if(data[i].currencies[0].code==="USD")
            {
                console.log("name:",data[i].name,"==>",data[i].currencies[0].code)
            }
        }
    }
