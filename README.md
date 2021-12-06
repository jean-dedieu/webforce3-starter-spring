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
	
#### Retourner les données d'une API 


          @SpringBootApplication
         @RestController
          public class DemoApplication {
	  public static void main(String[] args) {
		SpringApplication.run(DemoApplication.class, args);
	   }
	
	  @GetMapping("/")
	  @ResponseBody
	   public List<String> home(){
		//String home()
		//List<String>home()
		return List.of("Hello", "World","WebForce","Spring");
		//return "Hello Word!!";
	}
	
	
	
#### Class Student pour les données de notre API


     package com.webforce3.demofullapp.student;

     import java.time.LocalDate;

      public class Student {
	private Long id;
	private String name;
	private String email;
	private LocalDate dob;
	private int age;

	public Student() {

	}

	public Student(Long id, String name, String email, LocalDate dob, int age) {
		this.id = id;
		this.name = name;
		this.email = email;
		this.dob = dob;
		this.age = age;

	}
	
	public Student(String name, String email, LocalDate dob, int age) {
	
		this.name = name;
		this.email = email;
		this.dob = dob;
		this.age = age;

	}

	public Long getId() {
		return id;
	}

	public void setId(Long id) {
		this.id = id;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public String getEmail() {
		return email;
	}

	public void setEmail(String email) {
		this.email = email;
	}

	public LocalDate getDob() {
		return dob;
	}

	public void setDob(LocalDate dob) {
		this.dob = dob;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}

	@Override
	public String toString() {
		return "Student [id=" + id + ", name=" + name + ", email=" + email + ", dob=" + dob + ", age=" + age
				+ ", getId()=" + getId() + ", getName()=" + getName() + ", getEmail()=" + getEmail() + ", getDob()="
				+ getDob() + ", getAge()=" + getAge() + ", getClass()=" + getClass() + ", hashCode()=" + hashCode()
				+ ", toString()=" + super.toString() + "]";
	}

        }


#### DemoApplication for Student Class


         package com.webforce3.demofullapp;

         import java.time.LocalDate;
         import java.time.Month;
         import java.util.List;

        import org.springframework.boot.SpringApplication;
        import org.springframework.boot.autoconfigure.SpringBootApplication;
        import org.springframework.web.bind.annotation.GetMapping;
        import org.springframework.web.bind.annotation.ResponseBody;
        import org.springframework.web.bind.annotation.RestController;

        import com.webforce3.demofullapp.student.Student;



        @SpringBootApplication
        @RestController
        public class DemoApplication {
	public static void main(String[] args) {
		SpringApplication.run(DemoApplication.class, args);
	}
	
	@GetMapping("/")
	@ResponseBody
	public List<Student> home(){
		//String home()
		//List<String>home()
		//return List.of("Hello", "World","WebForce","Spring");
		//return "Hello Word!!";
		return List.of(
				new Student(
						1L,
						"Jean",
						"Dupond",
						LocalDate.of(2000, Month.JANUARY, 5),
						26
						)
				);
	          }
               }

