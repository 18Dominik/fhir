# fhir
this repository describes how to handle public available api REST schemas

## Importing the JSON Schema with the example of FHIR
 FHIR by HL7 is described as a 'RESTful' specification based on common industry level use of the term REST for healthcare interoperability
 
1.
![image](https://github.com/18Dominik/fhir/assets/35842490/6ce50dfb-0eb8-4f00-abbb-334f74d45695)
*Download JSON schema to verify that resources are valid and add .json to your working directory*
Set up VSCode to recognize FHIR schema
   
   ![image](https://github.com/18Dominik/fhir/assets/35842490/005df728-af63-49cc-bd4e-deda36d76f13)

   *open by Ctrl + Shift + P
   Select "json.schemas" and autocomplete with Ctrl + Space. Apply for all files with ```*.fhir.json``` and Set relative url path to downloaded schema*

2. Example to convert in FHIR resource:
   Name: Andrea White
   Gender: Female
   Date of Birth: 08. February 2000
   Phone: +6015733597
   Email: a.white@gmail.com
   Address: Rexington Street 529, 60875 Pittsburgh, USA
3. Add a new Patient file according to the example with ```patient.fhir.json``` and see how you can utilize the autocomplete from the [fhir schema for resource types with the example of "Patient"](https://build.fhir.org/patient.html)
   
4. Add a new patient according to the schema
    ![image](https://github.com/18Dominik/fhir/assets/35842490/bec5091a-bcf6-4886-b306-11b398126d6c)

   
   ![image](https://github.com/18Dominik/fhir/assets/35842490/66ceddbb-d35b-49ee-8e45-568a46c3516d)

    *Example for data type "HumanName*
5. Post new Patient resource to FHIR server using [publicly available FHIR servers for testing](https://confluence.hl7.org/display/FHIR/Public+Test+Servers)
   here we use R4 Endpoint of HAPI FHIR Reference Server: http://hapi.fhir.org/baseR4. Make a post request and copy Patient JSON into body (select JSON for body) and post it via Patient-endpoint http://hapi.fhir.org/baseR4/Patient, for
   example using [postman](https://www.postman.com/). You will get  HTTP code 201 (created) response and an id, for me it is 44403565 for this patient. Making a get request on this id with http://hapi.fhir.org/baseR4/Patient/44403565, you will get your patient.
6. This time, we create a new resource type, Observation. Post with http://hapi.fhir.org/baseR4/Observation and make a Get request including Patient ID like http://hapi.fhir.org/baseR4/Observation/44403587
   



   
## Good to know
[REST Maturity Model by Leonard Richardson](https://martinfowler.com/articles/richardsonMaturityModel.html)
![image](https://github.com/18Dominik/fhir/assets/35842490/1d28b845-9fbb-47b4-ba69-02a2302c0476)

