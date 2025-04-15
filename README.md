def nth_root(number, n, precision=0.0001):
    """
    Calculate the nth root of a number using Newton's method
    
    Parameters:
    number (float): The number to find the root of
    n (int): The degree of the root
    precision (float): The desired precision of the result
    
    Returns:
    float: The nth root of the number
    """
    if number < 0 and n % 2 == 0:
        raise ValueError("Cannot calculate even root of negative number")
    
    guess = number
    while True:
        new_guess = ((n - 1) * guess + number / (guess ** (n - 1))) / n
        if abs(new_guess - guess) < precision:
            return new_guess
        guess = new_guess
