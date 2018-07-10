# Inset조정(Padding)

## UILabel 의 경우,

	import UIKit
	
	class sampleLabel: UILabel {
	
	 let topInset = CGFloat(5.0), bottomInset = CGFloat(5.0), leftInset = CGFloat(8.0), rightInset = CGFloat(8.0)
	
	 override func drawTextInRect(rect: CGRect) {
	
	  let insets: UIEdgeInsets = UIEdgeInsets(top: topInset, left: leftInset, bottom: bottomInset, right: rightInset)
	  super.drawTextInRect(UIEdgeInsetsInsetRect(rect, insets))
	
	 }
	 override func intrinsicContentSize() -> CGSize {
	  var intrinsicSuperViewContentSize = super.intrinsicContentSize()
	  intrinsicSuperViewContentSize.height += topInset + bottomInset
	  intrinsicSuperViewContentSize.width += leftInset + rightInset
	  return intrinsicSuperViewContentSize
	 }
	}
	On ViewController:
	
	override func viewDidLoad() {
	  super.viewDidLoad()
	
	  let labelName = sampleLabel(frame: CGRectMake(0, 100, 300, 25))
	  labelName.text = "Sample Label"
	  labelName.backgroundColor =  UIColor.grayColor()
	
	  labelName.textColor = UIColor.redColor()
	  labelName.shadowColor = UIColor.blackColor()
	  labelName.font = UIFont(name: "HelveticaNeue", size: CGFloat(22))
	  self.view.addSubview(labelName)
	 }
	 
	 
##  UITextField의 경우,

	searchTextField.textRectForBounds(searchTextField.bounds)
	searchTextField.editingRectForBounds(searchTextField.bounds)
        
	 class SearchTextField: UITextField {
    let inset: CGFloat = 5
    
    // placeholder position
    override func textRectForBounds(bounds: CGRect) -> CGRect {
        return CGRectInset(bounds , inset , inset)
    }
    
    // text position
    override func editingRectForBounds(bounds: CGRect) -> CGRect {
        return CGRectInset(bounds , inset , inset)
    }
    
    override func placeholderRectForBounds(bounds: CGRect) -> CGRect {
        return CGRectInset(bounds, inset, inset)
    }
}
 
##  UITextView의 경우,

textview.textContainerInset = UIEdgeInset() // textcontainerinset은 텍스트뷰에서 컨텐츠 영역에 공간을 더 만든다는 것을 의미하며 기본값은 (8, 0, 8, 0).   
or  
textview.contentInset = UIEdgeInset() // contentInset은 스크롤 뷰 안에서 공간을 더 만든다는 것을 의미하며 기본값은 제로