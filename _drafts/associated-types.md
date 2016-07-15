Here's the case where I want to write a viewController `MainViewController` that accepts a datasource object as a property `datasource`. This object conforms to a protocol `CollectionDataSource`.

So here's what we have:

```
protocol CollectionDataSource: UICollectionViewDataSource {
    associatedtype ObjectType
    func objectAtIndexPath(indexPath:NSIndexPath) -> ObjectType?
    func refresh()
    func bindCollectionView(collectionView:UICollectionView)
    func objectsCount() -> Int
}

class MainViewController {
  var dataSource: CollectionDataSource?
}

let vc = MainViewController()
let indexPath = NS
vc.dataSource.objectAtIndexPath(indexPath)  
```
