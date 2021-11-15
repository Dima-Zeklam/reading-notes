# RecyclerView for displaying lists of data

- **RecyclerView** is a container used for displaying large amount of data sets that can be scrolled very efficiently by maintaining a limited number of views.

- **RecyclerView** improves performance, improving your app's responsiveness and reducing power consumption.

### There is Several different classes work together to build your dynamic list:

1. `RecyclerView` class is the ViewGroup that contains the views corresponding to your data.

2.  `RecyclerView.ViewHolder` an static abstract class extends *Object*,  After the view holder is created, the RecyclerView binds it to its data.

3. `RecyclerView.Adapter` class Adapters provide a binding from an app-specific data set to views that are displayed within a RecyclerView.

4. `LayoutManager` abstract class  is responsible for measuring and positioning item views within a RecyclerView as well as determining the policy for when to recycle item views that are no longer visible to the user. The RecyclerView library provides three layout managers:
* `LinearLayoutManager` arranges the items in a one-dimensional list.
* `GridLayoutManager` arranges all items in a two-dimensional grid.
* `StaggeredGridLayoutManager`The result is that the items in a row or column can end up offset from each other.

### Implementing your adapter and view holder
* A *ViewHolder* describes an item view and metadata about its place within the RecyclerView
* First define your adapter.
* Then override three key methods:
   * onCreateViewHolder()
   * onBindViewHolder()
   * getItemCount()
   
#### Read More about [Advanced RecyclerView customization ](https://developer.android.com/guide/topics/ui/layout/recyclerview-custom)




































