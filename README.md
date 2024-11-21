# Ex02 Django ORM Web Application
# Date:
# AIM
To develop a Django application to store and retrieve data from a bank loan database using Object Relational Mapping(ORM).

# ENTITY RELATIONSHIP DIAGRAM
## DESIGN STEPS
## STEP 1:
Clone the problem from GitHub

## STEP 2:
Create a new app in Django project

## STEP 3:
Enter the code for admin.py and models.py

## STEP 4:
Execute Django admin and create details for 10 books

# PROGRAM

# bank_loan_app/models.py
    from django.db import models
    
    class Loan(models.Model):
        loan_id = models.AutoField(primary_key=True)
        customer_name = models.CharField(max_length=100)
        loan_amount = models.DecimalField(max_digits=10, decimal_places=2)
        interest_rate = models.DecimalField(max_digits=5, decimal_places=2)
        loan_term = models.IntegerField()
        disbursement_date = models.DateField()


# bank_loan_app/admin.py
    from django.contrib import admin
    from .models import Loan
    
    admin.site.register(Loan)


# bank_loan_app/views.py
    from django.shortcuts import render
    from .models import Loan
    
    def loan_list(request):
        loans = Loan.objects.all()
        return render(request, 'loan_list.html', {'loans': loans})
    
    
    <h1>Loan List</h1>
    <table>
        <thead>
            <tr>
                <th>Customer Name</th>
                <th>Loan Amount</th>
                <th>Interest Rate</th>
                <th>Loan Term</th>
                <th>Disbursement Date</th>
            </tr>
        </thead>
        <tbody>
            {% for loan in loans %}
            <tr>
                <td>{{ loan.customer_name }}</td>
                <td>{{ loan.loan_amount }}</td>
                <td>{{ loan.interest_rate }}%</td>
                <td>{{ loan.loan_term }}</td>
                <td>{{ loan.disbursement_date }}</td>
            </tr>
            {% endfor %}
        </tbody>
    </table>



# OUTPUT
Include the screenshot of your admin page.

# RESULT
Thus the program for creating a database using ORM hass been executed successfully
