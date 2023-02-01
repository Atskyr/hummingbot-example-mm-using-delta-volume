from hummingbot.strategy.market_making_mode import MarketMakingMode
from hummingbot.market.delta.delta_market import DeltaMarket
from decimal import Decimal

class DeltaMarketMaker(MarketMakingMode):
    def __init__(self, delta_market: DeltaMarket, bid_spread: Decimal, ask_spread: Decimal):
        super().__init__(delta_market)
        self._bid_spread = bid_spread
        self._ask_spread = ask_spread
    
    def get_price(self, is_buy: bool):
        if is_buy:
            return self.price + self._bid_spread
        else:
            return self.price - self._ask_spread

delta_market_maker = DeltaMarketMaker(delta_market, Decimal("0.01"), Decimal("0.01"))
delta_market_maker.run()
