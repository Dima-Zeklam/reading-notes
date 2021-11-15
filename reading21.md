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

#### Example code:

```
public class CustomAdapter extends RecyclerView.Adapter<CustomAdapter.ViewHolder> {

    private String[] localDataSet;

    /**
     * Provide a reference to the type of views that you are using
     * (custom ViewHolder).
     */
    public static class ViewHolder extends RecyclerView.ViewHolder {
        private final TextView textView;

        public ViewHolder(View view) {
            super(view);
            // Define click listener for the ViewHolder's View

            textView = (TextView) view.findViewById(R.id.textView);
        }

        public TextView getTextView() {
            return textView;
        }
    }

    /**
     * Initialize the dataset of the Adapter.
     *
     * @param dataSet String[] containing the data to populate views to be used
     * by RecyclerView.
     */
    public CustomAdapter(String[] dataSet) {
        localDataSet = dataSet;
    }

    // Create new views (invoked by the layout manager)
    @Override
    public ViewHolder onCreateViewHolder(ViewGroup viewGroup, int viewType) {
        // Create a new view, which defines the UI of the list item
        View view = LayoutInflater.from(viewGroup.getContext())
                .inflate(R.layout.text_row_item, viewGroup, false);

        return new ViewHolder(view);
    }

    // Replace the contents of a view (invoked by the layout manager)
    @Override
    public void onBindViewHolder(ViewHolder viewHolder, final int position) {

        // Get element from your dataset at this position and replace the
        // contents of the view with that element
        viewHolder.getTextView().setText(localDataSet[position]);
    }

    // Return the size of your dataset (invoked by the layout manager)
    @Override
    public int getItemCount() {
        return localDataSet.length;
    }
}
```

#### Read More about [Advanced RecyclerView customization ](https://developer.android.com/guide/topics/ui/layout/recyclerview-custom)




































