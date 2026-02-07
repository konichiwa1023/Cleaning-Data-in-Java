public class GroceryDataQuality {
    public static void main(String[] args) {
        Table inventory = Table.read().csv("grocery_inventory.csv");

        for (String colName : inventory.columnNames()) {
            // Extract the column and count missing values in the column
            int missing = inventory.column(colName).countMissing();
            System.out.println(colName + " missing values: " + missing);
        }

        // Count the inventory by unique categories
        Table catCounts = inventory.countBy("Category");
        System.out.println("\nCategory distribution:");
        System.out.println(catCounts);
    }
}
