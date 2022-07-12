### Fixing 'VirtualizedLists should never be nested inside simple ScrollViews' warning

In some cases, we feel the need to use the scrollview along with the flatlist.

Then we generate the error by adding the flatlist inside a scrollview, but that's not necessary, just use ListHeaderComponent for the content above the list and ListFooterComponent for the content below.

Example of use:

```ts
<FlatList
  LisHeaderComponent={
    <View style={{ flex: 1 }}>
      <Text>Header content</Text>
    </View>
  }
  data={itemData}
  renderItem={renderItem}
  ListFooterComponent={
    <View style={{ flex: 1 }}>
      <Text>Footer content</Text>
    </View>
  }
/>
```
