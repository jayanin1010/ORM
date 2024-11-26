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

# PROGRAM:

# bank_loan_app\models.py

  from django.db import models
  from django.contrib import admin
  
  class Loan(models.Model):
      loan_id = models.AutoField(primary_key=True)
      customer_name = models.CharField(max_length=100)
      loan_amount = models.DecimalField(max_digits=10, decimal_places=2)
      interest_rate = models.DecimalField(max_digits=5, decimal_places=2)
      loan_term = models.IntegerField()
      disbursement_date = models.DateField()
  
  class LoanAdmin(admin.ModelAdmin):
  list_display=('loan_id','customer_name','loan_amount','interest_rate','loan_term','disbursement_date')


# bank_loan_app\admin.py


  from django.contrib import admin
  from .models import Loan,LoanAdmin
  
  admin.site.register(Loan,LoanAdmin)



# OUTPUT

![Screenshot 2024-11-22 084017](https://github.com/user-attachments/assets/e659a870-3123-45f5-8092-eb2d19064ad1)


# RESULT
Thus the program for creating a database using ORM hass been executed successfully
