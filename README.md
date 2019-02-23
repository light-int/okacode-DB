# okacode-DB
Api d'okacode seul les vrais savent
### Infos
my-json-server.typicode est un faux server REST en ligne pour les equipes
### Demarer le fake server 
         my-json-server.typicode.com/nom_utilisateur_github/repository/

Dans le cas du server d'Okacode ce sera

_my-json-server.typicode.com/light-int/okacode-DB/_

        {
        "id":1,
        "nom":"MENDE",
        "prenom":"Dimitri",
        "desc":"Coach de la cohorte des developpeur Web",
        "img":"https://lacastafiore.github.io/ecole241/okacode/images/Kakashi.jpg",
        "link":"#"
       },
	     {
        "id":2,
        "nom":"OBAME NZOGHO",
        "prenom":"Billy Marc Paul",
        "desc":"Tout ce qui est beau m'attire, j'aime donc la creativite, le travail, le code, et surtout la vie",
        "img":"https://lacastafiore.github.io/ecole241/okacode/images/Billy.jpg",
        "link":"https://light-int.github.io/ecole241/profil/index.html"
	     }
       
Et pour avoir un seul profil

_my-json-server.typicode.com/light-int/okacode-DB/1_ 

        {
        "id":1,
        "nom":"MENDE",
        "prenom":"Dimitri",
        "desc":"Coach de la cohorte des developpeur Web",
        "img":"https://lacastafiore.github.io/ecole241/okacode/images/Kakashi.jpg",
        "link":"#"
       }  
### Iteration 
pour recuperer tous les profiles nous allons faire une iteration a la methode **_each()_** de jquery en utilisant une requete ajax avec la methode _**$.getJSON**_

       //pointeur de la div qui a l'id all
       var el = $('#all');
       //Debut de la requete
       $.getJSON('https://my-json-server.typicode.com/light-int/okacode-DB/', function(data) {
        $.each(data , function (index, value){
          el.append('<div class="col-3"><div class="card"><img class="card-img-top" src="https://imgplaceholder.com/640x540" alt=""><div class="card-body"><h5 class="card-title">'+value.username+'</h5><p class="card-text">'+value.accountType+'</p><a name="" id="" class="btn btn-primary" href="profil.html?c='+value.id+'" role="button">voir</a></div></div></div>');
          // console.log(index + ':' + value.first_name);
          });
          console.log(window.location);
       });
       
 Voir la [demo](https://my-json-server.typicode.com/light-int/hackaton-DB/user)
