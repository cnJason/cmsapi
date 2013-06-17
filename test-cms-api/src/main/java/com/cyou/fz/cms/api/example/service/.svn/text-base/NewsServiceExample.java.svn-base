package com.cyou.fz.cms.api.example.service;

import java.util.HashMap;
import java.util.Map;

import org.springframework.context.support.ClassPathXmlApplicationContext;

import com.cyou.fz.cms.api.commons.dto.CmsQueryResult;
import com.cyou.fz.cms.api.service.NewsService;
import com.cyou.fz.cms.api.service.dto.NewsDTO;

/**
 * 新闻实例.
 * 
 */
public class NewsServiceExample {
	/**
	 * 查询新闻实例.
	 * @return 返回新闻列表信息.
	 */
	public  CmsQueryResult<NewsDTO> queryNews() {
		//配置文件的读取可以直接读取，也可以使用Spring的配置文件读取。
		//如果不用Spring，也可以直接采用dubbo中提供的非Spring方式读取。
		ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext(
				"classpath:comsumer.xml");
		context.start();
		NewsService newsService = (NewsService) context.getBean("newsService");
		// 设置条件，注释掉的代码是例子参考。
		Map<String, String> condition = new HashMap<String, String>();
//		condition.put("newsChannel", "10009");
//		condition.put("newsClass", "");
//		condition.put("newsKind", "");
//		condition.put("keyWord", "");
		return  newsService.queryNews(condition,1, 10);
	}
	
	/**
	 * 查询新闻实例.
	 * @return 返回单个新闻信息.
	 */
	public  NewsDTO getNews(){
		ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext(
				"classpath:comsumer.xml");
		context.start();
		NewsService newsService = (NewsService) context.getBean("newsService");
		//需要传递的参数，新闻Id
		int newsId = 123;
		return newsService.getNews(newsId);
	}
}
