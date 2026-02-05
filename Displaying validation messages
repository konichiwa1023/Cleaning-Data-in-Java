public class VideoGameSale {
    @NotNull(message = "Name cannot be empty")
    private String name;
    @NotNull(message = "Platform cannot be empty")
    private String platform;
    @Min(value = 1960, message = "Year must be greater than 1960")
    private Integer year;
    @Min(value = 0, message = "Sales amount must be positive")
    private Double sales;

    public VideoGameSale(String name, String platform, Integer year, Double sales) {
        this.name = name;
        this.platform = platform;
        this.year = year;
        this.sales = sales;
    }

    public static void main(String[] args) {
        VideoGameSale sale = new VideoGameSale(
                "Super Mario Bros.", null, 1950,
                -29.08);
        Set<ConstraintViolation<VideoGameSale>> violations =
                SalesValidator.validateSale(sale);
        // Print the violation message
        violations.forEach(violation ->
                System.out.println(violation.getMessage()));
        if (!violations.isEmpty()) throw new ConstraintViolationException(violations);
    }
}

class SalesValidator {
    private static final ValidatorFactory factory =
          Validation.buildDefaultValidatorFactory();
    private static final Validator validator = factory.getValidator();
    public static Set<ConstraintViolation<VideoGameSale>> validateSale(VideoGameSale sale) {
        // Validate the video game sale
        return validator.validate(sale);
    }
}
