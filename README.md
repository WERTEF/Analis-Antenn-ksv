# Analis-Antenn-ksv
Analisator Antenn ksv
# Code for CSV Antenna Analyzer
import csv
import matplotlib.pyplot as plt

def analyze_antenna_csv(csv_file_path):
    # Read CSV file
    with open(csv_file_path, 'r') as file:
        reader = csv.reader(file)
        rows = list(reader)

    # Extract data from CSV
    frequencies = [float(row[0]) for row in rows[1:]]  # Assuming the first column is frequency
    s11_values = [float(row[1]) for row in rows[1:]]    # Assuming the second column is S11 values

    # Plot the S11 values
    plt.plot(frequencies, s11_values)
    plt.title("Antenna S11 Values")
    plt.xlabel("Frequency (Hz)")
    plt.ylabel("S11 Values")
    plt.show()

# Example usage
csv_file_path = "path/to/your/antenna_data.csv"
analyze_antenna_csv(csv_file_path)
