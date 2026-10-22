# Create sample raw data
data <- data.frame(
  Name = c(" Rahul ", "Priya", "Amit", "Neha"),
  Age = c(21, 22, NA, 23),
  Salary = c(30000, 35000, 28000, NA)
)

# Display raw data
print(data)

# Remove extra spaces
data$Name <- trimws(data$Name)

# Replace missing ages with mean age
data$Age[is.na(data$Age)] <- mean(data$Age, na.rm = TRUE)

# Replace missing salaries with mean salary
data$Salary[is.na(data$Salary)] <-
  mean(data$Salary, na.rm = TRUE)

# Add annual salary category
data$Category <- ifelse(
  data$Salary >= 30000,
  "High",
  "Low"
)

# Display cleaned data
print(data)

# Export cleaned data
write.csv(data, "cleaned_data.csv", row.names = FALSE)



sales <- data.frame(
  Product = c("Laptop", "Mobile", "Tablet", "Monitor"),
  Sales = c(50000, 30000, 20000, 25000),
  Profit = c(10000, 7000, 4000, 5000)
) 

sales <- data.frame(
  Product = c("Laptop", "Mobile", "Tablet", "Monitor"),
  Sales = c(50000, 30000, 20000, 25000),
  Profit = c(10000, 7000, 4000, 5000)
)

ggplot(sales, aes(x = Product, y = Sales)) +
  geom_bar(stat = "identity") +
  labs(
    title = "Sales by Product",
    x = "Product",
    y = "Sales"
  )

  monthly_sales <- data.frame(
  Month = 1:6,
  Sales = c(10000, 15000, 12000, 18000, 22000, 25000)
)

ggplot(monthly_sales, aes(x = Month, y = Sales)) +
  geom_line() +
  geom_point() +
  labs(title = "Monthly Sales Trend")

  ggplot(sales, aes(x = Sales, y = Profit)) +
  geom_point() +
  labs(title = "Sales vs Profit")
