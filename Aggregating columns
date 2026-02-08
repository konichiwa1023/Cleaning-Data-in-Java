public class GroceryDataAggregation {
    public static void main(String[] args) {
        Table inventory = Table.read().csv("grocery_inventory.csv");

        Table quantityByCategory = inventory
                // Find expensive items (price > $5.00)
                .where(inventory.doubleColumn("Unit_Price").isGreaterThan(5.0))
                // Calculate total stock for each category
                .summarize("Stock_Quantity", sum)
                // Group results by product category
                .by("Category");

        System.out.println("Total quantity by category:");
        System.out.println(quantityByCategory.first(5));
    }
}
