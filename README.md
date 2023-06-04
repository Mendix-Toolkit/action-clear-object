## Clear Object

### Object attribute cleaner

![Mx Toolkit license badge](https://img.shields.io/github/license/Mendix-Toolkit/action-clear-object) ![Action Type badge](https://img.shields.io/badge/Category-JavaAction-green) ![Action Type badge](https://img.shields.io/badge/Category-JavascriptAction-green) ![Mendix Version Badge](https://img.shields.io/badge/Mendix-v9.6.x-blue)

## Use Case

### Revert all object attributes to an empty state

## Installation Guide

### Import Module

- Download the latest attached Mendix module package in `Releases` section
- Import the module into your Mendix project

### OR

### Manual installation

- Create a Java Action in Mendix
- Create Create Parameters as listed in `Usage Instructions`
- Run your application
- Copy the action code into your newly created JavaAction
- Change the `package` and `class` names and  to match your module and action names respectively

## Usage Instructions

### Parameter values

#### Java_ClearObject

| Parameter               | Type    | Description    |
|-------------------------|---------|----------------|
| logNode                 | String  | Mendix Console Log Message Node    |
| targetObject            | Object  | Object to have its' attributes cleared    |
| clearAssociations       | Boolean | Flag to empty owned associations    |
| clearSystemMembers      | Boolean | Flag to empty System Members (`createdDate`, `changedDate`, `changedBy`, and `owner`)    |
| commitObject            | Boolean | Flag to commit target object afterwards <br> ⚠ Committing a cleared object will overwrite its values in the Database  |

#### JS_ClearObject

| Parameter               | Type    | Description    |
|-------------------------|---------|----------------|
| targetObject            | Object  | Object to have its' attributes cleared    |
| clearAssociations       | Boolean | Flag to empty owned associations    |
| commitObject            | Boolean | Flag to commit target object afterwards <br> ⚠ Committing a cleared object will overwrite its values in the Database  |

#### ⚠ ClearObject is different from `Rollback` behavior, as it will empty attribute values instead of undoing uncommited changes
#### ⚠ ClearObject will always reset Boolean attributes to `false` value
#### ⚠ ClearObject will always reset Numeric attributes to `0` value
#### ⚠ ClearObject will skip attribute of type `AutoNumber`

#### ⚠ Java_ClearObject will disregard `Current_User` access permissions
#### ⚠ JS_ClearObject will adhere to `Current_User` access permissions

### Guide

### 🛈 Refer to the attached release file for a working example

#### Java_ClearObject

- Use ClearObject Java Action in a Microflow
- Fill in `logNode` to customize the resulting console message
- Pass the targeted object object as `targetObject`
- Set `clearAssociations`, `clearSystemMembers`,  and `commitObject` as required

#### JS_ClearObject

- Use ClearObject JS Action in a Nanoflow
- Log node will be the default Mendix `Client` node
- Pass the targeted object object as `targetObject`
- Set `clearAssociations` and `commitObject` as required

## Compatibility

### >= Mendix v9.6.17

## Helpful resources

#### - [Mendix Java Programming](https://docs.mendix.com/refguide/java-programming/)
#### - [Mendix Java Action Call](https://docs.mendix.com/refguide/java-action-call/)
#### - [Menidx Javascript Actions](https://docs.mendix.com/refguide/javascript-actions/)

## Changelog

- v1.0.0 Clear Object Java Action Release
- v1.1.0 Added JS_ClearObject and modified numeric values handling in Java_ClearObject
