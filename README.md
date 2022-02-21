# Swagger_SpringBoot
Create Swagger Api Doc For Springboot Project

    1).Get Dependencys in https://mvnrepository.com/ and Adding the Maven Dependency in pom.xml

        * springfox-swagger-ui
        * springfox-swagger2
        
    2).Configuration
    
      *.Create SwaggerConfig Class
      
      
            @Configuration
            @EnableSwagger2
            public class SwaggerConfig {

              @Bean
              public Docket productApi() {
                Docket docket =
                 new Docket(DocumentationType.SWAGGER_2).select()
                          .apis(RequestHandlerSelectors.basePackage("lk.sasanka")).build().apiInfo(apiEndPointsInfo());

                return docket;
              }
    
              private ApiInfo apiEndPointsInfo() {
              return new ApiInfoBuilder().title("Sasanka API")
                  .description("Api Doc")
                  .contact(new Contact("Sasanka", "sasankageek.tk", "kalana@sasankageek.tk"))
                  .license("Apache 2.0")
                  .licenseUrl("http://www.apache.org/licenses/LICENSE-2.0.html")
                  .version("1.0.0")
                  .build();
           }
          }
      
      
    3).Now we can test it in our browser by visiting
    
       http://localhost:yourPort/swagger-ui.html#/
       
       

    * boot version 2.6 or higher Not working properly (2022.2.21)
            https://stackoverflow.com/questions/70036953/springboot-2-6-0-spring-fox-3-failed-to-start-bean-documentationpluginsboot/70037507#70037507
