#### **Input** 
1. **Location Type**: Within University / Outside University
 - **If Within University**:
    2. Destination (Cengal, Dahlia, Kesinai, Beringin)
    3. Item Type (Glass, Electronic, Food/Drinks)
    4. Item Condition (Fragile, Delicate, Liquid, Perishable, Flammable, Keep Up-Right, Sensitive Material)
        - _(Multiple selections allowed)_
        - _If Item Type is "Glass", auto-select "Fragile"_
    5. Packaging Type (Envelope, Cardboard Box, Plastic Film, Plastic Box, Styrofoam)
    6. Bubble Wrapping (Wrapped / Not Wrapped)
        - _If Not Wrapped, prompt: “Would you like to add bubble wrapping?” (+RM1 to Total Cost)_
    7. Shipping Type (Standard / Express)
    8. Membership Status (Y/N)
		- If Y, apply discount
#### **Process** 
1. **Check Location Type**:
    - If "Outside University", skip other steps and go to Output (Line 292).
    - Else, continue with delivery setup.
2. Determine destination charge based on selected destination.
3. Validate Item Type and Item Condition:
    - If Item Type is "Glass", auto-select "Fragile".
4. Check bubble wrap status and add RM1 if user opts to include it.
5. Determine Shipping Fee:
    - Standard == RM3
    - Express == RM5
6. Check Membership:
    - If Yes, apply 10% discount to total cost.
7. Compute Total Cost:
    - Total Cost = Destination Charge + Shipping Fee + Bubble Wrap (if added) – Membership Discount (if any)
8. Repeat for the next user (Line 252)
#### **Output** 
- **If Location Type is Outside University**:
    - Message: “Please use Pos Laju or other services for shipping outside of University.”
    - Loop back to Input Step 1 (Line 252).
- **If Location Type is Within University**:
    - Display Summary:
        - Destination
        - 
        - Item Type & Conditions
        - Packaging Type
        - Bubble Wrap Status
        - Shipping Type
        - Membership Discount (if any)
    - Display **Total Cost**
