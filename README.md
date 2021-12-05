# webforce3-starter-spring

Créer un package

Créer une classe PagesControlles

Ajouter des annotations et une méthode


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
