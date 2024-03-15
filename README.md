# Library Member Management System

This project is a Java application designed to manage member information for a library.

## Classes

The project consists of the following classes:

* **Crud:** Handles database queries, including inserts, updates, deletes, and selects.
* **DbConnection:** Establishes and manages the database connection.
* **MemberManagementForm:** Provides the graphical user interface for interacting with member data.

## Functionality

The application supports the following functionalities:

* **Adding new members:**
* **Searching for members by ID:**
* **Viewing member details in a table:**
* **Updating member information:**
* **Deleting members:**

## My Work

 ### NAME: M.A.F.HAKEEMA
 ### REG.NO: KEG/IT/2021/F/0052

I added a couple features to our library's member management system that let users delete member records from the database. This feature facilitates simple management of member data, which improves system efficiency.

## Code Snippets

***You can look here some functions and events which i contribute to the group***
```java

    private void clearForm() {
        txtMemberId.setText("");
        txtName.setText("");
        txtPhoneNumber.setText("");
        txtEmail.setText("");
        txtAddress.setText("");
    }

    private void btnDeleteActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_btnDeleteActionPerformed
        try {
            Crud.execute("DELETE FROM member WHERE member_id=?", txtId.getText());
            JOptionPane.showMessageDialog(this, "Member deleted successfully!");
            txtId.setText("");
            clearForm();
            loadMembersIntoTable();
        } catch (SQLException | ClassNotFoundException ex) {
            JOptionPane.showMessageDialog(this, "Error deleting member. Please check the member ID and try again.", "Error", JOptionPane.ERROR_MESSAGE);
            Logger.getLogger(MemberManagementForm.class.getName()).log(Level.SEVERE, null, ex);
        }
    }//GEN-LAST:event_btnDeleteActionPerformed

