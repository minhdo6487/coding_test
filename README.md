1. Install [Python 3](https://www.python.org/) for your OS.

2. cd to workdir and activate python

3. Please take a look on this file `Coding Challenge Python.pdf` first

4. Please take a look on tests.py, I've prepare some test cases

5. Please find main function at `find_products_packages.py`
- sample input
    + is_ok, result = get_package([3, 5, 9], 13)
- sample output
    + True, [(0, 9), (2, 5), (1, 3)]
    + with 3 items in list
        - (0, 9): 
            + 0 x 9 @ $16.99
        - (2, 5):
            + 2 x 5 @ $9.95
        - (1, 3):
            + 1 x 3 @ $5.95


6. To define another packs and order_number, run command `python find_products_packages.py <packs: type List> <order_number: Int>`
=> for example: `python find_products_packages.py [2,3,8,14] 20`


p/s: Explan step
    product_list: [3, 5, 8] 
    product_order: 65
    
    floor 8 = (65 / 8) # with 8 is max(product_list)
    modulo 1
    => can not find any product, decrease from floor 8 to floor 7
    
    floor 7 
    modulo 9
    products [3 5] # product_list has been pop max value
    max 5 # at this time max(product_list) is 5
    remain 9 # because: 9 = 65 - (7 x 8)
    sum 8 # at this time 8 is sum(product_list)
    9 < 8 => False 
    9 / 5
    
    1st item
    [7 X 8]
    
        order_num is 9
        product [3 5]
        floor 1
        modulo 4
        remain 4
        pros = deepcopy(product)
        pros = [3 , 5]
        products [3]
        4 < 3 False
            len(product) == 1 and modulo == 1
            func([3,5], 9, calibrate=1)
                calibrate = 1
                order_num is 9
                product [3 5]
                floor 0
                modulo 4
                remain = 9
                pros = deepcopy(product)
                products = [3]
                9 < 3 False
                    [0, 5]
                    func([3,], 9, calibrate=0)
                    3rd imte
                        [3 , 3]
