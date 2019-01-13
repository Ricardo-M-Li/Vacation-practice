# Vacation-practice
package cn.shuise.xml.dom4j;



import java.util.List;

import org.dom4j.Document;
import org.dom4j.DocumentException;
import org.dom4j.Element;
import org.dom4j.io.SAXReader;
import org.junit.Test;

public class TestDom4j {
	@Test
	public void testReadWebXML(){
		try {
				//获取解析器
				SAXReader sReader = new SAXReader();
				//2.获得document文档对象
				Document doc =  sReader.read("src/cn/shuise/xml/schema/web.xml");
				//3.获取根元素
				 Element rootElements = doc.getRootElement();
				// System.out.println(rootElements.getName());//获取根元素名称
				//System.out.println(rootElements.attributeValue("version"));//获取根元素属性值
				//4.获取根元素下子元素
				List<Element> childElements = rootElements.elements();
				//5.遍历子元素
				 for (Element element : childElements) {
					 //6.判断元素名称为servlet的元素
					if("servlet".equals(element.getName()))
					{
						//获取servlet-name
						Element servletName = element.element("servlet-name");
						//获取servlet-class
						Element servletClass = element.element("servlet-class");
						System.out.println(servletName.getText());
						System.out.println(servletClass.getText());
					}
				}
		} catch (DocumentException e) {
			
		}
	}
}
