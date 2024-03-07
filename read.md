Primeira busca fiz utilizando o Query view (e não o json view)
Simplesmente busquei pela palavra "party" e não retornou nenhum resultado
Depois busquei pela palavra "donuts" e retornou o seguinte json:
{
  "@odata.context": "https://lab-ai-search.search.windows.net/indexes('coffee-index')/$metadata#docs(*)",
  "@odata.count": 1,
  "value": [
    {
      "@search.score": 0.8247094,
      "content": "Review: I heard that Fourth Coffee had the best seasonal donuts, so I ordered a dozen for my team for an event. Everyone loved them, I’ll definitely order again! \nDate: October 25, 2018\nLocation: Seattle, Washington \n\n",
      "metadata_storage_path": "aHR0cHM6Ly9zdG9yYWdlMGxhYjBhaS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlLXJldmlld3MvcmV2aWV3LTkuZG9jeA2",
      "locations": [
        "Seattle",
        "Washington"
      ],
      "keyphrases": [
        "best seasonal donuts",
        "Fourth Coffee",
        "Review",
        "dozen",
        "team",
        "event",
        "Everyone",
        "Date",
        "October",
        "Location",
        "Seattle",
        "Washington"
      ],
      "sentiment": "[\"positive\"]",
      "merged_content": "Review: I heard that Fourth Coffee had the best seasonal donuts, so I ordered a dozen for my team for an event. Everyone loved them, I’ll definitely order again! \nDate: October 25, 2018\nLocation: Seattle, Washington \n\n",
      "text": [],
      "layoutText": [],
      "imageTags": [],
      "imageCaption": []
    }
  ]
}

Percebi que localizou através do keyphrases.

Após alterei para JSON view e busquei o json abaixo onde gostaria de buscar nas tags das imagens que tivessem plantas verdes
{
  "search": "green plants",
  "count": true
}

a busca retornou o seguinte json:
{
  "@odata.context": "https://lab-ai-search.search.windows.net/indexes('coffee-index')/$metadata#docs(*)",
  "@odata.count": 1,
  "value": [
    {
      "@search.score": 0.8031771,
      "content": "\n\n\nReview: My favorite part about going to Fourth Coffee is the atmosphere. I love the warm lights and plants. It’s a great place to go get a cup of coffee while working on your next business idea or with friends at school. It’s also right next to the University hub, which makes it so easy to access for students. It just gets so busy on the weekends! I wish it was not so crowded. Since they started offering amazing breakfast sandwiches, I wouldn’t try to go get a coffee Saturday morning.  \nDate: September 1, 2018\nLocation: Los Angeles, California \nimage1.png\n\n\n\nimage2.png\n\n\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9zdG9yYWdlMGxhYjBhaS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlLXJldmlld3MvcmV2aWV3LTIuZG9jeA2",
      "locations": [
        "school",
        "University hub",
        "Los Angeles",
        "California"
      ],
      "keyphrases": [
        "next business idea",
        "amazing breakfast sandwiches",
        "favorite part",
        "warm lights",
        "great place",
        "University hub",
        "Los Angeles",
        "Fourth Coffee",
        "Review",
        "atmosphere",
        "plants",
        "cup",
        "friends",
        "school",
        "students",
        "weekends",
        "Date",
        "September",
        "Location",
        "California"
      ],
      "sentiment": "[\"positive\"]",
      "merged_content": "\n\n\nReview: My favorite part about going to Fourth Coffee is the atmosphere. I love the warm lights and plants. It’s a great place to go get a cup of coffee while working on your next business idea or with friends at school. It’s also right next to the University hub, which makes it so easy to access for students. It just gets so busy on the weekends! I wish it was not so crowded. Since they started offering amazing breakfast sandwiches, I wouldn’t try to go get a coffee Saturday morning.  \nDate: September 1, 2018\nLocation: Los Angeles, California \nimage1.png\n  \n\n\nimage2.png\n T \n\n\n",
      "text": [
        "",
        "T"
      ],
      "layoutText": [
        "{\"language\":\"en\",\"text\":\"\",\"lines\":[],\"words\":[]}",
        "{\"language\":\"en\",\"text\":\"T\",\"lines\":[{\"boundingBox\":[{\"x\":809,\"y\":32},{\"x\":837,\"y\":31},{\"x\":836,\"y\":56},{\"x\":808,\"y\":55}],\"text\":\"T\"}],\"words\":[{\"boundingBox\":[{\"x\":815,\"y\":31},{\"x\":831,\"y\":31},{\"x\":831,\"y\":56},{\"x\":815,\"y\":56}],\"text\":\"T\"}]}"
      ],
      "imageTags": [
        "wall",
        "indoor",
        "furniture",
        "clothing",
        "interior design",
        "person",
        "kitchen & dining room table",
        "countertop",
        "desk",
        "ceiling",
        "stool",
        "coffee table",
        "floor",
        "woman",
        "window",
        "table",
        "kitchen",
        "chair",
        "room",
        "cafe",
        "furniture",
        "indoor",
        "interior design",
        "houseplant",
        "wall",
        "house",
        "floor",
        "coffee table",
        "musical instrument",
        "table",
        "chair",
        "flooring",
        "clothing",
        "musical keyboard",
        "couch",
        "studio couch",
        "person",
        "room",
        "plant",
        "piano",
        "ceiling",
        "home"
      ],
      "imageCaption": [
        "{\"tags\":[\"indoor\",\"wall\",\"floor\",\"ceiling\"],\"captions\":[{\"text\":\"a person sitting at a table\",\"confidence\":0.53540337085723877}]}",
        "{\"tags\":[\"floor\",\"indoor\",\"living\",\"room\",\"plant\",\"furniture\",\"dining table\"],\"captions\":[{\"text\":\"a person sitting in a chair\",\"confidence\":0.43682509660720825}]}"
      ]
    }
  ]
}