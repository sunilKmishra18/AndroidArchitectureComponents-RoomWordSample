# Android Room with a View - Kotlin: Sample App

Here is a short introduction to the Architecture Components and how they work together.

**App Architecture:**




![Image of App Architecture](app-architecture.png)




The components of the app are:
- **`MainActivity`**: displays words in a list using a RecyclerView and the WordListAdapter. In the MainActivity, there is an Observer that observes the words LiveData from the database and is notified when they change.
- **`NewWordActivity`**: adds a new word to the list.
- **`WordViewModel(*)`**: provides methods for accessing the data layer, and it returns LiveData so that MainActivity can set up the observer relationship.
- **`LiveData<List<Word>>`**: Makes possible the automatic updates in the UI components. In the MainActivity, there is an Observer that observes the words LiveData from the database and is notified when they change.
- **`Repositor`y**: manages one or more data sources. The Repository exposes methods for the ViewModel to interact with the underlying data provider. In this app, that backend is a Room database.
- **`Room`**: is a wrapper around and implements a SQLite database. Room does a lot of work for you that you used to have to do yourself.
- **`DAO`**: maps method calls to database queries, so that when the Repository calls a method such as getAllWords(), Room can execute SELECT * from word_table ORDER BY word ASC.
- **`Word`**: is the entity class that contains a single work.


(*) **`Views and Activities (and Fragments)`** only interact with the data through the `ViewModel`. As such, it doesn't matter where the data comes from.





