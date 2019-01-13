# Vacation-practice
package shuise.xml.dpm4j;

import javax.swing.text.Document;
import javax.xml.bind.Element;

import org.dom4j.io.SAXReader;
import org.junit.Test;

public class TestDom4j {
	@Test
	public void testReadWebXML(){
		try {
			//获取解析器
			SAXReader sReader = new SAXReader();
			//2.获得document文档对象
			Document doc = (Document) sReader.read("src=shuise/xml/schema/web.xml");
			//3.获取根元素
			javax.swing.text.Element[] rootElement = doc.getRootElements();
		} catch (Exception e) {
			
		}
	}
}
