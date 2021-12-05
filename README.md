# webforce3-starter-spring

### Créer un package avec Controllers

### main method


     public static void main(String[] args) {
		SpringApplication.run(FirstAppApplication.class, args);
	}
	
	
	
#### Créer une classe PagesControlles et Ajouter des annotations et une méthode


       @Controller
      public class PagesController {
	     //creating methods
	     //execute the code when / called with GET METHOD
	     @GetMapping("/")
	    @ResponseBody
     	public String home() {
		
	    	return "Hello World";
	   }

     }


#### Créer une méthode pour mapper l'Url des articles


	@GetMapping("/articles")
	@ResponseBody
	public String articles() {
		return "Page des articles";
	}
