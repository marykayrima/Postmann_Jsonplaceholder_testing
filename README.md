# Postmann_Jsonplaceholder_testing
https://jsonplaceholder.typicode.com/todos/

              //return all
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

                       //return by ID
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Validation of ID", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.id).to.eql(4);
});
pm.test("Status code name has string OK", function () {
    pm.response.to.have.status("OK");
});

                    //check true data
pm.test("Validation of title", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.title).to.eql("incidunt ut saepe autem");
});

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Validation of ID", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.id).to.eql(86);
});

                //  negativ case: non-exsisted element
pm.test("array is empty", function () {
    pm.response.to.have.body("{}");
});

pm.test("Status code is 404", function () {
    pm.response.to.have.status(404);
});
