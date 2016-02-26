---
layout: post
---

<html lang="en">
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
		<meta http-equiv="x-ua-compatible" content="ie=edge">
		<meta name="msvalidate.01" content="89359D9C492A475C0061398008D105FB" />
		
		<!-- seo !-->
		<meta name="description" content="Dramatically improve query performance and overcome SQL limitations with Eval Function">
		<meta name="keywords" content="Eval, Evaluate, Compile, Execute, Expression, Dynamic, Runtime, .NET, dotnet, C#, CSharp, VB, Stored Procedure, Procedure, Function, Trigger, SQL">
		<title>SQL Eval Function | Improve SQL Server query performance and dynamically evaluate expression using C# syntax.</title>
		
		<!-- icon/css !-->
		<link rel="icon" type="image/png" href="http://entityframework-plus.net/images/logo.png">
		<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.2/css/bootstrap.min.css" integrity="sha384-y3tfxAZXuh4HwSYylfB+J125MxIs6mR5FOHamPBG064zB+AFeWH94NdvaCBm8qnd" crossorigin="anonymous">
		<link rel="stylesheet" type="text/css" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
		<link rel="stylesheet" type="text/css" href="http://entityframework-plus.net/css/github2.css">
		<link rel="stylesheet" type="text/css" href="http://entityframework-plus.net/css/default.css">
	</head>
	
	<body>
  
		<!-- top-header !-->
		<div id="top-header">
			<div class="container">
				<div class="text-right">
					<a href="mailto:info@zzzprojects.com"><i class="fa fa-envelope"></i>&nbsp;&nbsp;info@zzzprojects.com</a>
					<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
					<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
					<a href="https://plus.google.com/+Zzzprojects_NetSQL" target="_blank"><i class="fa fa-google-plus"></i></a>
					<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank" class="hidden-xs-down"><i class="fa fa-newspaper-o"></i></a>
				</div>
			</div>
		</div>
		
		<!-- header !-->
		<header>
			<div class="container">
				<div class="row">
					<div class="col-lg-6">
						<div class="card">
							<div class="card-block">
								<h3 class="card-title">Eval SQL.NET</h3>
								<hr class="m-y-md" />
								<h1>Dramatically improve query performance and overcome SQL limitations with Eval Function</h1>
								<hr class="m-y-md" />
								<div class="lead">
									<a href="https://github.com/zzzprojects/Eval-SQL.NET/releases" target="_blank" class="btn btn-success btn-lg btn-left" role="button" onclick="ga('send', 'event', { eventAction: 'download'});"><span><i class="fa fa-cloud-download fa-2x"></i>&nbsp;<span>Download</span></span></a>
									<a href="https://github.com/zzzprojects/Eval-SQL.NET" target="_blank" class="btn btn-primary btn-lg btn-right" role="button" onclick="ga('send', 'event', { eventAction: 'github'});"><span><i class="fa fa-github fa-2x"></i>&nbsp;<span>GitHub</span></span></a>
									<p class="text-muted">* FREE Version limited to 50 characters</p>						
								</div>
							</div>
						</div>
					</div>
					<div class="col-lg-6">
						<div class="card">
							<div class="card-block card-code">
{% highlight sql %}
-- Evaluate dynamically expression in T-SQL
DECLARE @tableFormula TABLE (
   Formula VARCHAR(255), X INT, Y INT, Z INT
)

INSERT  INTO @tableFormula VALUES ('x+y*z', 1, 2, 3 ), 
                                  ('(x+y)*z', 1, 2, 3 )
-- SELECT 7
-- SELECT 9
SELECT SQLNET::New(Formula)
              .ValueInt('x', X)
              .ValueInt('y', Y)
              .ValueInt('z', Z).EvalInt()
FROM @tableFormula
{% endhighlight %}	
							</div>
						</div>
					</div>
				</div>
			</div>
		</header>
		
		<!-- featured !-->
		<div id="featured">
			<div class="container">
			
				<!-- SQL Eval Function like JavaScript !-->
				<h2>SQL Eval Function like JavaScript</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="featured-tagline">Avoid using slow user-defined function (UDF) and table-valued function (TVF) and dramatically improve query performance with Eval SQL.NET.</p>
						<ul class="featured-list-sm">
							<li>Execute SQL <span class="text-bold-red">3-20x faster</span> than UDF and TVF</li>
							<li>Evaluate an expression more than <span class="text-bold-red">ONE MILLION</span> times under a second</li>
							<li>Evaluate expression using C# Syntax</li>
						</ul>
					</div>
					<div class="col-lg-7">
						<table class="table table-striped table-hover" style="background-color: white;">
							<tr class="thead-inverse">
								<th>Methods</th>
								<th>1,000 Rows</th>
								<th>10,000 Rows</th>
								<th>100,000 Rows</th>
								<th>1,000,000 Rows</th>
							</tr>
							<tr>
								<th>Eval SQL.NET</th>
								<td>4 ms</td>
								<td>13 ms</td>
								<td>160 ms</td>
								<td>1,650 ms</td>
							</tr>
							<tr>
								<th>fn_split (TVF)</th>
								<td>100 ms</td>
								<td>625 ms</td>
								<td>5,500 ms</td>
								<td>55,000 ms</td>
							</tr>
						</table>
						
						<p>* Benchmark to split a text with a delimiter</p>
					</div>
				</div>
			</div>
		</div>
		
		<!-- testimonials !-->
		<div id="testimonials">
			<div class="container">
				<h2>Amazing <span class="text-bold-red">performance</span>, unmatched <span class="text-bold-red">flexibility</span>, outstanding <span class="text-bold-red">support</span>!</h2>
				<ul>
					<li>- "We were very, very pleased with the customer support. There was no question, problem or wish, that was not answered AND solved within days! We think that’s very unique!" Klemens Stelzmüller, <a href="http://www.beka-software.at/" target="_blank">Beka-software</a></li>
					<li>- "I’d definitely recommend it, as it is a great product with a great performance and reliability." Eric Rey, <a href="http://www.transturcarrental.com/" target="_blank">Transtur</a></li>
				</ul>
				<p><span class="text-bold-red">Share</span> your experience, we love to hear from you: <a href="mailto:info@zzzprojects.com">info@zzzprojects.com</a></p>
			</div>
		</div>
		
		<!-- features !-->
		<div id="feature">
			<div class="container">
				<!-- Evaluate dynamic arithmetic/math expression in SQL!-->
				<a id="evaluate-dynamic-arithmetic-math-expression-in-sql" href="#"></a>
				<h2>Evaluate dynamic arithmetic/math expression in SQL</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Make the impossible now possible. Evaluate C# expression in SQL to overcome limitations.</p>
						<ul>
							<li>Allow trusted users to create report field and filter</li>
							<li>Consume Web Service</li>
							<li>Replace text in template with String Interpolation</li>
						</ul>
					</div>
					<div class="col-lg-7">
{% highlight sql %}
-- CREATE test
DECLARE @table TABLE ( X INT, Y INT, Z INT )
INSERT  INTO @table VALUES  ( 2, 4, 6 ),  ( 3, 5, 7 ), ( 4, 6, 8 )

-- Result: 14, 22, 32
DECLARE @sqlnet SQLNET = SQLNET::New('x*y+z')
SELECT  @sqlnet.ValueInt('x', X)
               .ValueInt('y', Y)
               .ValueInt('z', Z)
               .EvalInt()
FROM    @table
{% endhighlight %}
					</div>
				</div>

				<hr class="m-y-md" />
				
				<!-- Split text with delimiter !-->
				<a id="split-text-with-delimiter" href="#"></a>
				<h2>Split text with delimiter</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Improve <span class="text-bold-red">performance</span> and <span class="text-bold-red">capability</span> for splitting text with an easy to use split function and LINQ expressions.</p>
						<ul>
							<li>Split text with multiple delimiters</li>
							<li>Split text using a regular expression</li>
							<li>Include row index</li>
						</ul>
					</div>
					<div class="col-lg-7">
{% highlight sql %}
-- CREATE test
DECLARE @t TABLE (Id INT , Input VARCHAR(MAX))
INSERT  INTO @t VALUES  ( 1, '1, 2, 3; 4; 5' ), ( 2, '6;7,8;9,10' )

-- SPLIT with many delimiters: ',' and ';'
DECLARE @sqlnet SQLNET = SQLNET::New('Regex.Split(input, ",|;")')

SELECT  *
FROM    @t AS A
        CROSS APPLY ( SELECT    *
                      FROM      dbo.SQLNET_EvalTVF_1(@sqlnet.ValueString('input', Input))
                    ) AS B
{% endhighlight %}	
					</div>
				</div>

				<hr class="m-y-md" />
				
				<!-- Use regular expression in SQL Server !-->
				<a id="use-regular-expression-in-sql-server" href="#"></a>
				<h2>Use regular expression in SQL Server</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Use Regex <span class="text-bold-red">flexibility</span> to overcome “LIKE” and “PATHINDEX” limitations.</p>
						<ul>
							<li>IsMatch</li>
							<li>Match</li>
							<li>Matches</li>
							<li>Replace</li>
							<li>Split</li>
						</ul>					
					</div>
					<div class="col-lg-7">
{% highlight sql %}
DECLARE @customer TABLE ( Email VARCHAR(255) )

INSERT  INTO @customer
VALUES  ( 'info@zzzprojects.com' ),
        ( 'invalid.com' ),
        ( 'sales@zzzprojects.com' )

DECLARE @valid_email SQLNET = SQLNET::New('Regex.IsMatch(email, 
@"^([a-zA-Z0-9_\-\.]+)@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.)|(([a-zA-Z0-9\-]+\.)+))([a-zA-Z]{2,4}|[0-9]{1,3})(\]?)$")')

-- SELECT 'invalid.com'
SELECT * FROM @customer WHERE @valid_email.ValueString('email', Email).EvalBit() = 0
{% endhighlight %}	
					</div>
				</div>	

				<hr class="m-y-md" />
				
				<!-- Replace xp_cmdshell with restrictive alternative !-->
				<a id="repalce-xp-cmdshell-with-restrictive-alternative" href="#"></a>
				<h2>Replace xp_cmdshell with restrictive alternative</h2>
				<div class="row">
					<div class="col-lg-5">
						<p class="feature-tagline">Avoid enabling xp_cmdshell and compromising your SQL Server and use instead a more <span class="text-bold-red">restrictive</span> solution.</p>
						<ul>
							<li>Impersonate Context</li>
							<li>Improve maintainability</li>
							<li>Improve readability</li>
							<li>Improve security</li>
						</ul>						
					</div>
					<div class="col-lg-7">
{% highlight sql %}
-- REQUIRE EXTERNAL_ACCESS permission
DECLARE @sqlnet SQLNET = SQLNET::New('
string path = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);

var dir = new DirectoryInfo(path);
return dir.GetFiles("*.*")
          .Select(x => new { x.FullName, FileContent = File.ReadAllText(x.FullName) })
          .OrderBy(x => x.FullName)')
          .Impersonate()

-- SELECT FullName, FileContext FROM DesktopFiles ORDER BY Fullname
EXEC dbo.SQLNET_EvalResultSet @sqlnet
{% endhighlight %}	
					</div>
				</div>	
			</div>
		</div>
		
		<!-- support !-->
		<a id="supports" href="#"></a>
		<div id="support">
			<div class="container">
				<h2>Test our outstanding Support</h2>
				<h3>We usually answer within the next business day, hour, or minutes!</h3>
				<div class="row">
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Contact Us</h4>
							</div>
							<a href="mailto:info@zzzprojects.com"><i class="fa fa-users fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Email our team for any type of questions. We love to hear from you!</p>
								<a href="mailto:info@zzzprojects.com">info@zzzprojects.com</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Documentation</h4>
							</div>
							<a href="https://github.com/zzzprojects/Eval-SQL.NET/wiki" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});"><i class="fa fa-folder-open fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Consult our complete documentation to help you getting started.</p>
								<a href="https://github.com/zzzprojects/Eval-SQL.NET/wiki" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});">Documentation</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Forum</h4>
							</div>
							<a href="https://github.com/zzzprojects/Eval-SQL.NET/issues" target="_blank" onclick="ga('send', 'event', { eventAction: 'forum'});"><i class="fa fa-weixin fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Visit the forum to propose new features or to discuss about the library.</p>
								<a href="https://github.com/zzzprojects/Eval-SQL.NET/issues" target="_blank" onclick="ga('send', 'event', { eventAction: 'forum'});">Forum</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Open Source</h4>
							</div>
							<a href="https://github.com/zzzprojects/Eval-SQL.NET" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});"><i class="fa fa-github fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Access the source of the library you're using to understand better its logic.</p>
								<a href="https://github.com/zzzprojects/Eval-SQL.NET" target="_blank" onclick="ga('send', 'event', { eventAction: 'github'});">GitHub</a>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
		
		<!-- pricing !-->
		<a id="pro" href="#"></a>
		<div id="pricing">
			<div class="container">
				<div class="row">
					<div class="col-lg-6">
						<h2>Pricing</h2>
						<hr class="m-y-md" />
						<p class="pricing-tagline">Eval SQL.NET is a safe, flexible and scalable solution to perform all dynamic operations.</p>
						<p class="pricing-tagline">Change "Mission Impossible" code to easy task and reduce your development cost and time.</p>
						<ul>
							<li>Improve <span class="text-bold-red">performance</span> over UDF & TVF</li>
							<li>Increase <span class="text-bold-red">maintainability</span> over complex SQL</li>
							<li>Increase <span class="text-bold-red">readability</span> over complex SQL</li>
						</ul>
						<p class="pricing-tagline">SQL developer are waited so long to get an Eval function, it's now possible and easy to perform all dynamic operations.</p>
						<hr class="m-y-md" />
						<p>Every month, a <a href="https://github.com/zzzprojects/Eval-SQL.NET/releases" target="_blank" onclick="ga('send', 'event', { eventAction: 'download'});">FREE trial</a> of the PRO version is available to let you evaluate all its features without limitations.</p>						
					</div>
					<div class="col-lg-6">
						<table class="table table-hover table-bordered">
							<thead class="thead-inverse">
								<tr>
									<th></th>
									<th>FREE</th>
									<th>PRO</th>
								</tr>
							</thead>
							<tbody>
								<tr>
									<th>Maximum Characters</th>
									<td>50</td>
									<td>Unlimited</td>
								</tr>
								<tr>
									<th>Commercial License</th>
									<td><i class="fa fa-times fa-2x"></i></td>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Support & Upgrades (1 year)</th>
									<td><i class="fa fa-times fa-2x"></i></td>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
							</tbody>
						</table>
						
						<form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top" onsubmit="return purchase_validate()">
							<input type="hidden" name="cmd" value="_s-xclick">
							<input type="hidden" name="hosted_button_id" value="H8RME3A5PQ5V6">
							<input type="hidden" name="currency_code" value="USD">
							<fieldset class="form-group">
								<input type="hidden" name="on0" value="Seats">
								<select name="os0" class="form-control">
									<option value="1 seat">Eval SQL.NET $599 (1 seat)</option>
									<option value="2-4 seats" selected>Eval SQL.NET $799 (2-4 seats)</option>
									<option value="5-9 seats">Eval SQL.NET $999 (5-9 seats)</option>
									<option value="10-14 seats">Eval SQL.NET $1199 (10-14 seats)</option>
									<option value="15-19 seats">Eval SQL.NET $1399 (15-19 seats)</option>
								</select> 
							</fieldset>
							<div class="checkbox">
								<label>
									<input id="agree_agreement" type="checkbox">I have read and agree to the <a href="http://www.zzzprojects.com/license-agreement/" target="_blank">License Agreement</a>.
								</label>
							</div>
							<button type="submit" class="btn btn-success btn-lg"><span><i class="fa fa-shopping-cart"></i>&nbsp;<span>BUY NOW</span></span></button>
							<div><br />* Contact us for invoice or payment method alternative.</div>
						</form>	
					</div>
				</div>
			</div>
			
			<!-- validation !-->
			<div id="error_validation" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="modal_agreement" aria-hidden="true">
				<div class="modal-dialog" role="document">
					<div class="modal-content">
						<div class="modal-header">
							<h4 class="modal-title" id="modal_agreement">License Agreement</h4>
						</div>
						<div class="modal-body bg-danger">
							You must read and agree to the License Agreement.
						</div>
						<div class="modal-footer">
							<button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
						</div>
					</div>
				</div>
			</div>
		</div>

		<!-- other product !-->
		<div id="product">
			<div class="container">
				<div class="row">
					<div class="col-lg-3">
						<h3>Entity Framework</h3>
						<ul>
							<li><a href="http://entityframework-extensions.net/" target="_blank">Entity Framework Extensions</a></li>
							<li><a href="http://entityframework-plus.net/" target="_blank">Entity Framework Plus (EF+)</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Bulk Operations</h3>
						<ul>
							<li><a href="http://bulk-operations.net/" target="_blank">Bulk Operations</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Expression Evaluator</h3>
						<ul>
							<li><a href="http://eval-sql.net/" target="_blank">Eval SQL.NET</a></li>
							<li><a href="http://eval-expression.net/" target="_blank">Eval Expression.NET</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Others</h3>
						<ul>
							<li><a href="https://github.com/zzzprojects/Z.ExtensionMethods" target="_blank">Extension Methods</a></li>
							<li><a href="https://github.com/zzzprojects/LINQ-Async" target="_blank">LINQ Async</a></li>
						</ul>
					</div>
				</div>
			</div>		
		</div>
		
		<!-- footer !-->
		<footer>
			<div class="container text-center-md-down">
				<div class="row">
					<div class="col-lg-6">
						Copyright © <a href="http://www.zzzprojects.com/" target="_blank" class="text-bold">ZZZ Projects Inc.</a> 2014 - 2016
						<div class="hidden-lg-up"></div>
						All rights reserved
					</div>
					<hr class="hidden-lg-up" />
					<div class="col-lg-6 text-right-lg-up social">
						<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
						<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
						<a href="https://plus.google.com/+Zzzprojects_NetSQL" target="_blank"><i class="fa fa-google-plus"></i></a>
						<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank"><i class="fa fa-newspaper-o"></i></a>
					</div>
				</div>
			</div>
		</footer>

	<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
	<script src="http://entityframework-plus.net/js/tether.min.js"></script>
	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.2/js/bootstrap.min.js" integrity="sha384-vZ2WRJMwsjRMW/8U7i6PWi6AlO1L79snBrmgiDpgIWJ82z8eA5lenwvxbMV1PAh7" crossorigin="anonymous"></script>
	<script type="text/javascript">
	  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
	  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
	  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
	  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

	  ga('create', 'UA-55584370-4', 'auto');
	  ga('send', 'pageview');
	  
	  function purchase_validate() {
		if($("#agree_agreement").prop('checked')) {
			return true;
		}
		
		$("#error_validation").modal('show')
		return false;
	  }
	</script>
	</body>
</html>
