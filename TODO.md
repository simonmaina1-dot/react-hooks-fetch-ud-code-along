# Implementation Plan: Update and Delete (CRUD) Operations

## Current State Analysis
- **ShoppingList.jsx**: Has READ (fetch items) and CREATE (via ItemForm) functionality
- **Item.jsx**: Contains UI with "Add to Cart" and "Delete" buttons but no event handlers
- **ItemForm.jsx**: CREATE functionality working
- **db.json**: Contains 6 items with `isInCart` property

## Changes Required

### 1. Update Feature (PATCH) - Add/Remove from Cart
**File: src/components/Item.jsx**
- [x] Add `onUpdateItem` prop to Item component
- [x] Create `handleAddToCartClick` function with PATCH fetch request
- [x] Attach onClick handler to "Add to Cart" button
- [x] Call onUpdateItem with updated item from server

**File: src/components/ShoppingList.jsx**
- [x] Create `handleUpdateItem` callback function
- [x] Use map to create new array replacing updated item
- [x] Pass `onUpdateItem` prop to Item component

### 2. Delete Feature (DELETE) - Remove item completely
**File: src/components/Item.jsx**
- [x] Add `onDeleteItem` prop to Item component
- [x] Create `handleDeleteClick` function with DELETE fetch request
- [x] Attach onClick handler to Delete button
- [x] Call onDeleteItem after successful deletion

**File: src/components/ShoppingList.jsx**
- [x] Create `handleDeleteItem` callback function
- [x] Use filter to create new array without deleted item
- [x] Pass `onDeleteItem` prop to Item component

### 3. Best Practices Documentation
- [x] Add comments to explain purpose and logic - DONE in code
- [x] Update README.md with functionality documentation - README already contains comprehensive documentation
- [x] Remove any unnecessary/commented code - Cleaned up unused useState import

## Implementation Order
1. [x] First: Update ShoppingList.jsx with callback functions
2. [x] Second: Update Item.jsx with event handlers and fetch requests
3. [x] Third: Verify functionality works correctly (run the app)
4. [x] Fourth: Add documentation comments and update README

## Completed Features
### Update (PATCH) - Add/Remove from Cart
- When user clicks "Add to Cart" button → PATCH request to toggle isInCart
- State updated using map() to maintain array order

### Delete (DELETE) - Remove item completely
- When user clicks "Delete" button → DELETE request to remove from server
- State updated using filter() to remove the item

## How to Run
```bash
# Terminal 1: Start json-server
npm run server

# Terminal 2: Start React app
npm run dev
```

Open http://localhost:3000 to test the application.

