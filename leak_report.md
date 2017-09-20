# Leak report
strip allocates memory for its result variable, you can't free result though 
since you return it in the same function. strip is called later on in 
is_clean as a variable cleaned, this is the variable you free. You need a 
conditional though since strip doesn't allocate memory al the time.'
