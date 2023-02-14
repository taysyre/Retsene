# Retsene Collaboration
Tyvon April
Sakhe Mzolisa

module.exports = {
    HOST = "bjetpev4a1i2qrl7svgv-mysql.services.clever-cloud.com",
    USER = "ulgskmeqhhi6wcyn",
    PASSWORD:"lJz0ndLm8bZxLIizStAo",
    DB: "bjetpev4a1i2qrl7svgv"
};

module.exports = app => {
    const tutorials = require("../controllers/tutorial.controller");

    var router = require("express").Router();

    //Create a new tutorial
    router.post("/", tutorials.create);

    //Retrieve all tutorials
    router.get("/", tutorials.findAll);

    //Retrieve all published tuts
    router.get("/published", tutorials.findAllPublished);

    //Retrieve a single tut with id
    router.get("/:id", tutorials.findOne);

    //update a tutorial with id
    router.put("/:id", tutorials.update);

    //Delete a tut with id
    router.delete("/:id", tutorials.delete);

    //Delete all tuts
    router.delete("/", tutorials.deleteAll);

    app.use('/api/tutorials', router);
};
