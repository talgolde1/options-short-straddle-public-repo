# Options Trading Algorithm

**Note: You are now visiting the public repository which contains the README only, please contact the author talgolde1@gmail.com in order to achieve access to the private project. As mentioned, This project is private. Please refrain from sharing the code or any sensitive information about the project.**

This project implements an options trading algorithm using the Interactive Brokers (IBKR) API and the `ib_insync` library. The algorithm aims to generate trading signals based on the analysis of implied volatility and other indicators. It allows automated trading of options contracts and provides functionality for monitoring positions, executing trades, and managing risk.

## Features

- Fetch historical and real-time market data from IBKR TWS.
- Calculate implied volatility Rank and other technical indicators.
- Execute option trades based on predefined high implied volatility rank strategies.
- Monitor open positions and orders on a minute basis.
- Manage risk through position P&L adjustments and monitoring and order cancellations.
- Generate logs and notifications for monitoring and debugging.

  ## Short Straddle Strategy

Description: 

The following strategy target is to be able to make a one standard deviation short straddle entry when the implied volatility rank (IVR) must be higher than 50. The strategy takes advantage of the elevated option premiums in a high implied volatility environment while also positioning the trade to be within one standard deviation of the underlying asset's current price.

The one standard deviation short straddle involves selling both  call options and put options with the same expiration date and strike price, but the strike price is set at one standard deviation away from the current strike price of the underlying asset. This positioning aims to increase the probability of the underlying asset staying within the profit zone of the trade.


![Short Straddle](https://www.fidelity.com/bin-public/600_Fidelity_Com_English/images/migration/shortstraddle600x340.png)


there are several advantages to the following strategy which are: 

- **Enhanced Premium Income** In a high implied volatility environment, options tend to have higher premiums. By selling both a call and a put option at the same strike price and expiration date, the short straddle allows the trader to collect more substantial premiums upfront. The increased premium income provides a cushion against potential losses and contributes to higher overall profitability.
- **Exploiting Time Decay** Short straddles benefit from time decay, also known as theta decay. As time passes, the extrinsic value of options diminishes, leading to a reduction in their premiums. Traders who have sold the straddle can profit from this time decay, especially when implied volatility is high and option premiums are inflated.
- **Neutral Strategy** The short straddle is a market-neutral strategy, meaning it is designed to generate profits regardless of the market direction. It thrives in a sideways or range-bound market, making it suitable for high implied volatility environments where the underlying asset's price is expected to remain relatively stable.
- **High Probability of Success** In high implied volatility environments, options are priced with larger anticipated price swings. The short straddle strategy benefits from the potential overpricing of these options due to inflated implied volatility. The trader can capitalize on the higher likelihood of options expiring out-of-the-money, leading to a higher probability of success.
- **Risk Management** Although the short straddle carries unlimited risk in theory, the increased premium received in a high implied volatility environment can help mitigate potential losses. The substantial upfront credit provides a buffer zone before the strategy becomes unprofitable. Additionally, the trader can implement stop-loss orders or manage the position actively to limit potential risks.

### Video Explanation

**[Short Straddle Video](https://www.youtube.com/watch?v=Lsk9ppb8ffs)**


**Watch this YouTube video for an in-depth explanation of the short straddle strategy and how it can be applied in various market conditions.**


## Requirements

To run the algorithm, the following components are required:

- Interactive Brokers (IBKR) account with API access.
- IBKR Trader Workstation (TWS) installed and running.
- Python 3.7 or higher.
- `ib_insync` library installed (`pip install ib_insync`).
- Other dependencies listed in the `requirements.txt` file.

## Configuration

Before running the algorithm, make sure to configure the following:

1. IBKR API connection: Specify the IP address and port of your TWS instance in the algorithm's configuration file.

2. Trading strategy: Define your desired trading strategy by configuring the indicators, thresholds, and rules in the algorithm's code.

3. Risk management: Set risk parameters, such as maximum position size, maximum loss limits, and stop loss levels, to control the algorithm's behavior.

## Usage

1. Clone the repository: `git clone https://github.com/your-username/options-trading-algorithm.git`

2. Install the dependencies: `pip install -r requirements.txt`

3. Configure the algorithm: Update the configuration file with your IBKR API connection details and desired trading strategy.

4. Run the algorithm: Execute the main script using `python main.py`.

5. Monitor logs and notifications: Check the program's console output, log files, and any configured notification channels for updates on trades, positions, and errors.

6. Adjust parameters and strategy: Fine-tune the algorithm's settings based on performance analysis and desired risk management approach.

   **Note: Make sure to add your Interactive Brokers account credentials to the `TradingAlgorithm` class before running the script.**

### Running the Algorithm
To run the algorithm, create an instance of the `TradingAlgorithm` class and call its `run_algorithm` method with a list of stock symbols as input.

**Example:**
```python
if __name__ == "__main__":
    algorithm = TradingAlgorithm()
    algorithm.run_algorithm(symbol_list=["AAPL", "AMZN", "GOOGL", ...])
```

## Contact Information
For any inquiries or concerns regarding this private project, please contact the project owner directly talgolde1@gmail.com.

## License

This project is private, and all rights are reserved by the project owner. Unauthorized distribution or use of the code is strictly prohibited.
This project is licensed under the [MIT License](LICENSE).

## Disclaimer

- This algorithm is provided for educational and informational purposes only. Use it at your own risk.
- Trading options involves financial risk, and past performance is not indicative of future results. Make sure to thoroughly understand the risks before engaging in real trading.
- The developer is not responsible for any losses or damages incurred as a result of using this algorithm.
- If you are unable to access the private repository which contains the project [Click here to access the private repository](https://github.com/talgolde1/options-short-straddle)
  make sure the author approved your access or else respect the wish of the project privacy or else legal actions will be concerned.

