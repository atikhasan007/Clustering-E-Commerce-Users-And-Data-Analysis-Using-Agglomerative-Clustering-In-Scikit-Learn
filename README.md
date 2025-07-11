from fpdf import FPDF

# Create PDF class
class PDF(FPDF):
    def header(self):
        self.set_font('Arial', 'B', 14)
        self.cell(0, 10, 'E-Commerce Customer Segmentation using Hierarchical Clustering', ln=True, align='C')
        self.ln(5)
    
    def chapter_title(self, title):
        self.set_font('Arial', 'B', 12)
        self.cell(0, 10, title, ln=True, align='L')
        self.ln(2)

    def chapter_body(self, body):
        self.set_font('Arial', '', 11)
        self.multi_cell(0, 8, body)
        self.ln()

# Create PDF
pdf = PDF()
pdf.add_page()

# Add content
content = [
    ("Problem Statement", 
     "To cluster users of an e-commerce platform based on their behavior (e.g., time spent, items added to cart, purchase history) and identify distinct customer types using Hierarchical Clustering."),

    ("Dataset", 
     "A realistic dummy dataset was created with 20 samples and 6 features:\n"
     "- Session_Duration: Duration of the user session (minutes)\n"
     "- Pages_Visited: Number of pages visited in the session\n"
     "- Items_in_Cart: Number of items added to the cart\n"
     "- Avg_Session_Value: Average value of the session (in dollars)\n"
     "- Time_Spent_on_Site: Time spent on the site (seconds)\n"
     "- Purchase_History: Total number of past purchases"),

    ("Technologies & Libraries Used", 
     "- Python\n- pandas, NumPy\n- scikit-learn\n- matplotlib, seaborn\n- scipy"),

    ("Steps Performed", 
     "1. Data Preparation: Created a dummy dataset and converted it to a pandas DataFrame.\n\n"
     "2. Standardization: Used StandardScaler to normalize feature values.\n\n"
     "3. Determine Optimal Clusters: Used Dendrogram with linkage method='ward'.\n\n"
     "4. Apply Agglomerative Clustering: n_clusters=2, metric='euclidean', linkage='ward'.\n\n"
     "5. Assign Cluster Names: Cluster 0 - 'Premium Customers', Cluster 1 - 'One-Time Browsers'.\n\n"
     "6. Visualize the Result: Scatter plot using Session_Duration vs Avg_Session_Value."),

    ("Conclusion", 
     "This project demonstrates how unsupervised learning can reveal valuable customer patterns in e-commerce businesses, helping in better targeting and decision-making.")
]

for title, body in content:
    pdf.chapter_title(title)
    pdf.chapter_body(body)

# Save the PDF
pdf_path = "/mnt/data/Ecommerce_Customer_Segmentation.pdf"
pdf.output(pdf_path)

pdf_path
