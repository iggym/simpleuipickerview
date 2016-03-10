# simpleuipickerview
# UIkit
UIPickerView

## Preview
![uipickerview](https://cloud.githubusercontent.com/assets/1582509/13684155/4b4443ea-e6bf-11e5-9101-8f7aaf8472d4.png)
## Source
ViewController.swift
```swift
import UIKit

class ViewController: UIViewController, UIPickerViewDelegate, UIPickerViewDataSource {

    // UIPickerView.
    private var myUIPicker: UIPickerView!

    @IBOutlet weak var sbUIPicker: UIPickerView?

    // values of picker
    private let myValues: NSArray = ["one","two","three","four"]

    override func viewDidLoad() {
        super.viewDidLoad()

        myUIPicker = UIPickerView()

        // set sie
        myUIPicker.frame = CGRectMake(0,0,self.view.bounds.width, 280.0)

        // set delegate
        myUIPicker.delegate = self

        // set DataSource
        myUIPicker.dataSource = self

        // add it to view
        self.view.addSubview(myUIPicker)
    }

    // data method to return the number of column shown in the picker.
    func numberOfComponentsInPickerView(pickerView: UIPickerView) -> Int {
        return 1
    }

    // data method to return the number of row shown in the picker.
    func pickerView(pickerView: UIPickerView, numberOfRowsInComponent component: Int) -> Int {
        return myValues.count
    }

    // delegate method to return the value shown in the picker
    func pickerView(pickerView: UIPickerView, titleForRow row: Int, forComponent component: Int) -> String? {
        return myValues[row] as? String
    }

    // delegate method called when the row was selected.
    func pickerView(pickerView: UIPickerView, didSelectRow row: Int, inComponent component: Int) {
        print("row: \(row)")
        print("value: \(myValues[row])")
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
    }
}
```
