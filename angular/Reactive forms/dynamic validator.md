# Dynamic validators Cheat Sheet
## Description
A way to dynamically set validators to a form control and to change a formControl depends on an other one
## Methods
setValidators : add new validators
oneControl.valueChanges.subscribe((res)) : watch value changes of an input field 
clearValidators: remove validators
updateValueAndValidity(): update input field validation status
## Examples
```typescript

    private initForm(){
    let isRequired = ( conditions ) ? true : false;
    // Create the a specific FormControl 
    const myControl = new FormControl(
      { value: null},
      [Validators.min(0)]
    );
    // Add Validators.required to 'myControl' if isRequired is true
    if (isRequired) {
      myControl.setValidators([Validators.min(0), Validators.required]);
    }
    // Watch for changes in the 'myControl' field and set Validators.required dynamically to 'secondControl'
    myControl.valueChanges.subscribe((value) => {
      if (value !== null && value !== '') {
        this.form.get('secondControl').setValidators([Validators.required]);
      } else {
        this.form.get('secondControl').clearValidators();
      }
      // Update the 'secondControl' field's validation status
      this.form.get('secondControl').updateValueAndValidity();
    });
    this.form = new FormGroup({
      myControl: amountControl,
      secondControl: new FormControl({value: null, disabled: isEnable}),
    });
  }

```