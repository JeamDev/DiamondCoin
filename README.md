# DiamondCoin

DiamondCoin is a Python library for working with the [DiamondCoin API](https://vk.com/@diamondcoinnn-diamond-api).

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install DiamondCoin.

```bash
pip install DiamondCoin
```

## Usage

```python
import DiamondCoin as dc

merchant = dc.DiamondCoin(user_id='your_user_id', key='your_key')

# Send payment
merchant.send_payment(to_id='receiver_user_id', amount='1000')

# Get payment URL
merchant.get_payment_url(amount=100)

# Get transactions
merchant.get_transactions(tx=[1])

# Get balance
merchant.get_balance()


# Remove callback endpoint
merchant.remove_callback_endpoint()

# Set callback endpoint
merchant.set_callback_endpoint(ip='your_ip_address', port=8080)

# Get top users
merchant.get_top(top_type='user')

# Run callback server
merchant.run_callback()

# Payment handler
@merchant.payment_handler(handler_type='longpoll')
def payment_callback_handler(payment_data):
    print(payment_data)

merchant.run_longpoll(tx=[1])
or 
merchant.run_longpoll(tx=[2])
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)