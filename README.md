Here's an example of code using API to reduce coupling between components, with comments removed:

```python
class DataService:
    def get_data(self):
        # Placeholder method to get data from data source
        pass

class BusinessLogic:
    def __init__(self, data_service):
        self.data_service = data_service

    def process_data(self):
        data = self.data_service.get_data()
        # Business logic to process data
        pass

class PresentationLayer:
    def __init__(self, business_logic):
        self.business_logic = business_logic

    def show_data(self):
        self.business_logic.process_data()
        # Presentation logic to show data
        pass

if __name__ == "__main__":
    # Create instances of components
    data_service = DataService()
    business_logic = BusinessLogic(data_service)
    presentation_layer = PresentationLayer(business_logic)

    # Use the presentation layer to interact with the system
    presentation_layer.show_data()
```

In this code:

- `DataService` is a class responsible for fetching data from a data source.
- `BusinessLogic` is a class that contains the logic to process the data obtained from the data service.
- `PresentationLayer` is a class responsible for presenting the processed data to the user.
- Each component depends on the interface provided by the component it interacts with, rather than on the implementation details.
- This design reduces coupling between components because each component depends only on the interfaces of the components it interacts with, rather than on their concrete implementations.
