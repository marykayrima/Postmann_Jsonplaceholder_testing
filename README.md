# Postmann_Jsonplaceholder_testing
https://jsonplaceholder.typicode.com/todos/

              //return all
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
pm.test("Status code name has string OK", function () {
    pm.response.to.have.status("OK");
});

var jsonData = pm.response.json();

pm.test("Json has more than 2 objects", function () {
    pm.expect(jsonData.length).to.least(2);
});
pm.test("Title of the first element is 'delectus aut autem'", function () {
    pm.expect(jsonData[0].title).to.eql("delectus aut autem");
});
pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});

                       //return by ID
                       
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
pm.test("Status code name has string OK", function () {
    pm.response.to.have.status("OK");
});


 var jsonData = pm.response.json();
 
pm.test("Check userID", function () {
   pm.expect(jsonData.userId).to.eql(1);
});
pm.test("Check id", function () {
   pm.expect(jsonData.id).to.eql(4);
});
pm.test("Check title", function () {
   pm.expect(jsonData.title).to.eql("et porro tempora");
});
pm.test("Check completed", function () {
   pm.expect(jsonData.completed).to.eql(true);
});

                   
                //  negativ case: non-exsisted element
                
pm.test("Check if empty", function () {
    pm.response.to.have.body("{}");
});

pm.test("Status code is 404", function () {
    pm.response.to.have.status(404);
});

pm.test("Status code name is Not Found ", function () {
    pm.response.to.have.status("Not Found");
});
