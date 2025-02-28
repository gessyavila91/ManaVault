This is a comprehensive refactor of the `GildedRose` codebase, with improvements aimed at achieving better maintainability and extensibility by following the **Single Responsibility Principle** and other clean code principles. Here's a summary of the changes:

### Overview of Changes:

1. **New `ProductUpdater` Interface**:    
    - Defined a contract for product-specific update logic.
2. **Factory Implementation**:
    - `ProductUpdaterFactory` determines the appropriate `ProductUpdater` implementation for each item based on its name.
3. **Abstract Base Class for Attribute Updates**:
    - `AbstractProductAttributesUpdater` provides reusable helper methods for common update operations like increasing/decreasing quality and sell-in.
4. **Specific Product Updaters**:
    - Each type of item (e.g., Aged Brie, Backstage Passes, Sulfuras) has its own updater class implementing the `update` method with logic tailored to its behavior.
5. **Integration with `GildedRose`**:
    - Simplified the `updateQuality` method to use the factory and delegate logic to the corresponding updater.
6. **New Test Suite**:
    - Added integration tests to validate the behavior of the `GildedRose` implementation with various item types.
---
### Key Benefits:
1. **Separation of Concerns**:
    - The `GildedRose` class is now responsible only for iterating over items and delegating update logic to the appropriate `ProductUpdater`.
2. **Extensibility**:
    - Adding support for new item types requires creating a new `ProductUpdater` implementation and updating the factory.
3. **Reusability**:
    - Shared logic is encapsulated in the abstract base class, reducing duplication.
4. **Testability**:
    - Each updater can be unit-tested independently, and integration tests ensure the system works as expected.
5. **Readability**:
    - The removal of large conditional blocks makes the `GildedRose` code much cleaner and easier to follow.
---
### Next Steps:
1. **Enhance Test Coverage**:
    - Verify edge cases (e.g., maximum quality limits, items with negative quality).
    - Add tests for newly added product types like "Conjured."
2. **Documentation**:
    - Document the responsibilities and usage of each component for developers who need to maintain or extend the system.
3. **Performance Optimizations** (if needed):
    - If the item list grows significantly, explore caching or batching strategies.