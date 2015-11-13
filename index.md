---
layout: post
---

<html lang="en">
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1">
		<meta http-equiv="x-ua-compatible" content="ie=edge">
		<meta name="description" content="Evaluate, Compile and Execute code and expression at runtime">
		<meta name="keywords" content="NET, CSharp, VB, Eval, Evaluate, Compile, Execute">
		<title>Evaluate, Compile and Execute code and expression at runtime</title>
		<link rel="icon" type="image/png" href="http://eval-sql.net/images/logo.png">
		<link rel="stylesheet" type="text/css" href="https://cdn.rawgit.com/twbs/bootstrap/v4-dev/dist/css/bootstrap.min.css">
		<link rel="stylesheet" type="text/css" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
		<link rel="stylesheet" type="text/css" href="/css/github.css">
	</head>
	<body>
  
	<a id="download" href="#"></a>
	<a id="github" href="#"></a>
	<div id="top-header">
		<div class="container">
			<div class="row">
				<div class="col-sm-12 text-right">
					<a href="mailto:sales@zzzprojects.com"><i class="fa fa-envelope"></i>&nbsp;sales@zzzprojects.com</a>
					<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
					<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
					<a href="https://plus.google.com/+Zzzprojects_NetSQL/posts" target="_blank"><i class="fa fa-google-plus"></i></a>
					<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank" class="hidden-sm-down"><i class="fa fa-newspaper-o"></i></a>
				</div>
			</div>
		</div>
	</div>
	<header>
		<div class="container">
			<div class="row">
				<div class="col-lg-6">
					<div class="jumbotron">
						<h1>Eval SQL.NET</h1>
						<h3>Evaluate code and expression using .NET in SQL stored procedure, function and trigger.</h3>
						<hr class="m-y-md" />
						<div class="lead">
							<a href="https://www.nuget.org/packages/Z.Expressions.Eval/" target="_blank" class="btn btn-success btn-lg btn-left" role="button"><span><i class="fa fa-cloud-download fa-2x"></i>&nbsp;<span>Download</span></span></a>
							<a href="https://github.com/zzzprojects/Z.Expressions.Eval" target="_blank" class="btn btn-primary btn-lg btn-right" role="button"><span><i class="fa fa-github fa-2x"></i>&nbsp;<span>GitHub</span></span></a>
							<p class="text-muted">* FREE Version - up to 50 characters</p>						
						</div>
					</div>
				</div>
				<div class="col-lg-6">
					<div id="carousel" class="carousel slide" data-ride="carousel" data-interval="4000">
						<ol class="carousel-indicators">
							<li data-target="#carousel" data-slide-to="0" class="active"></li>
							<li data-target="#carousel" data-slide-to="1" class=""></li>
						</ol>
						<div class="carousel-inner" role="listbox">
							<div class="carousel-item active">
								<div class="carousel-item-container">
{% highlight sql %}
CREATE PROCEDURE [dbo].[select_formula]
AS
BEGIN
    SELECT  SQLNET::New('x + y')
        .Val('x', ColumnValueX)
        .Val('y', ColumnValueY)
        .Eval()
    FROM TableFormula
END
{% endhighlight %}
								</div>
								<div class="carousel-caption">
									<h3>From simple expression...</h3>
								</div>
							</div>
							<div class="carousel-item">
								<div class="carousel-item-container">
{% highlight sql %}
CREATE PROCEDURE [dbo].[select_where_regex_filter]
AS
BEGIN
    DECLARE @sqlnet_filterFile SQLNET = SQLNET::New().SetCode('
    return Regex.IsMatch(filePath, "^.*\.(jpg|gif|docx|pdf)$");')

    SELECT  *
    FROM    [FileTable]
    WHERE   @sqlnet_filterFile.SetValue('filePath', FilePathColumn).Eval() = 1
END
{% endhighlight %}
								</div>
								<div class="carousel-caption">
									<h3>To complex.</h3>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</header>
	
	<div id="feature">
		<div class="container">
			<div class="row">
				<div class="col-lg-6">
					<a id="execute" href="#"></a>
					<h2>Eval</h2>
					<hr class="m-y-md" />
					<div class="block-code">
						<p>Evaluate the code or expression</p>
						<h3>Using Column Value</h3>
						<h3>Using Regex Class</h3>
					</div>
					<div class="text-center"><a class="btn btn-primary btn-lg" href="#" role="button">Learn More&nbsp;<i class="fa fa-hand-o-right"></i></a></div>
				</div>
				<div class="col-lg-6">
					<a id="compile" href="#"></a>
					<h2>EXEC EvalResultSet</h2>
					<hr class="m-y-md" />
					<div class="block-code">
						<p>Evaluate the code or expression and return the result set</p>
						<h3>Get desktop files</h3>
						<h3>Insert result in table</h3>
					</div>
					<div class="text-center"><a class="btn btn-primary btn-lg" href="#" role="button">Learn More&nbsp;<i class="fa fa-hand-o-right"></i></a></div>
				</div>
			</div>
		</div>
	</div>
	
	<div id="pricing">
		<div class="container">
			<div class="row">
				<div class="col-lg-6">
					<h2>Pricing</h2>
					<hr class="m-y-md" />
					<p>Become a <span class="text-bold text-green">PRO</span> now and start saving time and money!</p>
					<p>Thousands of <span class="text-bold">development hours</span> and thousands of <span class="text-bold">unit tests</span> to make Eval SQL.NET the best and most robust SQL evaluator for .NET language.</p>
					<p><i class="fa fa-gift fa-5x text-green"></i><span style="font-size:40px;" class="text-green">50% off</span>
					<p>
						PRO License starting at <span class="text-bold text-green">ONLY $299</span> <span style="text-decoration:line-through">$599</span>
						<br />
						<span class="text-muted">+$100/Additional developer seat <span class="text-italic">(Regular: $200)</span></span>
					</p>

					</p>
					<p>
					 *Hurry! This offer ends January 1st 2016.
					</p> 
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
								<th>Royalty-Free</th>
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
					
					<form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top" onsubmit="return validate()">
						<input type="hidden" name="cmd" value="_s-xclick">
						<input type="hidden" name="hosted_button_id" value="PW79CTHBQFBZC">
						<input type="hidden" name="currency_code" value="USD">
						<fieldset class="form-group">
							<input type="hidden" name="on0" value="Seats">
							<select name="os0" class="form-control">
								<option value="1 seat">Eval SQL.NET $299 (1 seat)</option>
								<option value="2 seats">Eval SQL.NET $399 (2 seats)</option>
								<option value="3 seats">Eval SQL.NET $499 (3 seats)</option>
								<option value="4 seats">Eval SQL.NET $599 (4 seats)</option>
								<option value="5-9 seats">Eval SQL.NET $699 (5-9 seats)</option>
								<option value="10-15 seats">Eval SQL.NET $899 (10-15 seats)</option>
							</select> 
							<span class="text-muted">* 50% discount is already applied</span>
						</fieldset>
						<div class="checkbox">
							<label>
								<input id="agree_agreement" type="checkbox">I have read and agree to the <a href="" target="http://www.zzzprojects.com/license-agreement/">License Agreement</a>.
							</label>
						</div>
						<button type="submit"  class="btn btn-success btn-lg" ><span><i class="fa fa-shopping-cart"></i>&nbsp;<span>BUY NOW</span></span></button>
					</form>					
				</div>
			</div>
		</div>
	</div>
	
	<a id="support" href="#"></a>
	<div id="support">
		<div class="container">
			<h2>Test our Outstanding Support</h2>
			<p>We usually answer within the next business day, hour, or minutes!</p>
			<div class="row">
				<hr class="hidden-sm-up" />
				<div class="col-sm-6 col-lg-3">
					<div class="card">
						<div class="card-block">
							<h4 class="card-title">Documentation</h4>
						</div>
						<a href="/docs/" target="_blank"><i class="fa fa-folder-open fa-5x"></i></a>
						<div class="card-block">
							<p class="card-text">Consult our complete documentation to help you get started</p>
							<a href="/docs/" target="_blank">Documentation</a>
						</div>
					</div>
				</div>
				<hr class="hidden-sm-up" />
				<div class="col-sm-6 col-lg-3">
					<div class="card">
						<div class="card-block">
							<h4 class="card-title">Contact Us</h4>
						</div>
						<a href="mailto:sales@zzzprojects.com"><i class="fa fa-users fa-5x"></i></a>
						<div class="card-block">
							<p class="card-text">Email our team for any type of questions. We love to hear from you!</p>
							<a href="mailto:sales@zzzprojects.com">sales@zzzprojects.com</a>
						</div>
					</div>
				</div>
				<hr class="hidden-sm-up" />
				<div class="col-sm-6 col-lg-3">
					<div class="card">
						<div class="card-block">
							<h4 class="card-title">Forum</h4>
						</div>
						<a href="mailto:sales@zzzprojects.com"><i class="fa fa-weixin fa-5x"></i></a>
						<div class="card-block">
							<p class="card-text">Visit the forum to propose new features or to discuss about the library</p>
							<a href="http://zzzprojects.uservoice.com/forums/328452-eval-sql-net" target="_blank">Forum</a>
						</div>
					</div>
				</div>
				<hr class="hidden-sm-up" />
				<div class="col-sm-6 col-lg-3">
					<div class="card">
						<div class="card-block">
							<h4 class="card-title">Open Source</h4>
						</div>
						<a href="https://github.com/zzzprojects/Eval-SQL.NET" target="_blank"><i class="fa fa-github fa-5x"></i></a>
						<div class="card-block">
							<p class="card-text">
							Access the source of the library you're using to understand better its logic</p>
							<a href="https://github.com/zzzprojects/Eval-SQL.NET" target="_blank">GitHub</a>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
	
	<div id="product">
		<div class="container">
			<div class="row">
				<div class="col-lg-3">
					<div class="product-section">Bulk Operations</div>
					<ul>
						<li><a href="#" target="_blank">.NET Entity Framework Plus</a></li>
						<li><a href="#" target="_blank">.NET Bulk Operations</a></li>
					</ul>
				</div>
				<div class="col-lg-3">
					<div class="product-section">Expression Evaluation</div>
					<ul>
						<li><a href="#" target="_blank">Eval.NET</a></li>
						<li><a href="#" target="_blank">Eval SQL.NET</a></li>
					</ul>
				</div>
				<div class="col-lg-3">
					<div class="product-section">Library</div>
					<ul>
						<li><a href="#" target="_blank">Extension Methods</a></li>
					</ul>
				</div>
			</div>
		</div>		
	</div>
	
	<footer>
		<div class="container">
			<div class="row">
				<div class="col-lg-6 text-center-md-down">
					Copyright © 2015 <a href="http://www.zzzprojects.com/" target="_blank">ZZZ Projects Inc.</a>
					<div class="hidden-lg-up"></div>All rights reserved
				</div>
				<hr class="hidden-lg-up" />
				<div class="col-lg-6 text-center-md-down text-right-lg-up social">
					<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
					<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
					<a href="https://plus.google.com/+Zzzprojects_NetSQL/posts" target="_blank"><i class="fa fa-google-plus"></i></a>
					<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank"><i class="fa fa-newspaper-o"></i></a>
				</div>
			</div>
		</div>
	</footer>
	
	<div id="error_validation" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
		<div class="modal-dialog" role="document">
			<div class="modal-content">
				<div class="modal-header">
					<h4 class="modal-title" id="myModalLabel">License Agreement</h4>
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

    <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
    <script type="text/javascript" src="https://cdn.rawgit.com/twbs/bootstrap/v4-dev/dist/js/bootstrap.min.js"></script>
	<script type="text/javascript">
	  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
	  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
	  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
	  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

	  ga('create', 'UA-55584370-3', 'auto');
	  ga('send', 'pageview');
	  
	  function validate() {
		if($("#agree_agreement").prop('checked')) {
			return true;
		}
		
		$("#error_validation").modal('show')
		return false;
	  }
	</script>
  </body>
</html>

<style>
/* general */
* {
	 font-family: "Bitter",Georgia,"Times New Roman",serif;
}
.highlight * {
	font-family: Consolas, "Liberation Mono", Menlo, Courier, monospace;
}
.text-bold {
	font-weight: 700;
}
.text-italic {
	font-style: italic;
}
.text-green {
	color: rgb(68, 157, 68);
}
@media (max-width: 61em) {
	.text-center-md-down {
		text-align: center;
	}
}
@media (max-width: 33em) {
	.text-center-xs-down {
		text-align: center;
	}
}
@media (min-width: 62em) {
	.text-right-lg-up {
		text-align: right;
	}
}
/* section general */
#top-header {
    background: -moz-linear-gradient(top, #111, #222);
    background: -webkit-linear-gradient(top, #111, #222);
    background: -ms-linear-gradient(top, #111, #222);
    background: -o-linear-gradient(top, #111, #222);
    background: linear-gradient(top, #111, #222);
	border-bottom: 1px solid #111;
	font-size: 14px;
	padding-top: 5px;
	padding-bottom: 5px;
}
header {
	background: -moz-linear-gradient(top, #222, #333);
    background: -webkit-linear-gradient(top, #222, #333);
    background: -ms-linear-gradient(top, #222, #333);
    background: -o-linear-gradient(top, #222, #333);
    background: linear-gradient(top, #222, #333);
	border-bottom: 1px solid #111;
	border-top: 1px solid #333;
}
#feature {
    background: -moz-linear-gradient(top, #ddd, #f2f2f2);
    background: -webkit-linear-gradient(top, #ddd, #f2f2f2);
    background: -ms-linear-gradient(top, #ddd, #f2f2f2);
    background: -o-linear-gradient(top, #ddd, #f2f2f2);
    background: linear-gradient(top, #ddd, #f2f2f2);
    border-top: 1px solid #eee;
	padding-bottom: 60px;
}
#pricing {
	background-color: #fefefe;
	padding-top: 60px;
	padding-bottom: 60px;
}
#support {
	background: -moz-linear-gradient(top, #eee, #bbb);
    background: -webkit-linear-gradient(top, #eee, #bbb);
    background: -ms-linear-gradient(top, #eee, #bbb);
    background: -o-linear-gradient(top, #eee, #bbb);
    background: linear-gradient(top, #eee, #bbb);
	padding-top: 60px;
	padding-bottom: 60px;
	border-bottom: 1px solid #aaa;
}
#product {
    background: -moz-linear-gradient(top, #111, #222);
    background: -webkit-linear-gradient(top, #111, #222);
    background: -ms-linear-gradient(top, #111, #222);
    background: -o-linear-gradient(top, #111, #222);
    background: linear-gradient(top, #111, #222);
	border-bottom: 1px solid #111;
	border-top: 1px solid #333;
	color: #f1f1f1;
	padding-top: 20px;
	padding-bottom: 20px;
}
footer {
	background: -moz-linear-gradient(top, #333, #222);
    background: -webkit-linear-gradient(top, #333, #222);
    background: -ms-linear-gradient(top, #333, #222);
    background: -o-linear-gradient(top, #333, #222);
    background: linear-gradient(top, #333, #222);
	border-top: 1px solid #444;
	color: #666;
	padding-top: 5px;
	padding-bottom: 5px;
}

/* top-header */
#top-header a {
	color: #f1f1f1;
	padding-left: 10px;
	padding-right: 10px;
	text-decoration: none;
} 
#top-header a:hover {
	opacity: 0.7;
    transition: all 0.4s ease-in-out 0s;
}

/* header */
header .jumbotron {
	background-color: transparent;
	color: #f1f1f1;
	margin-bottom: 0px;
	padding-top: 20px;
}
header .jumbotron h1 {
	font-size: 3.0rem;
	padding-top: 30px;
}
header .jumbotron h3 {
	font-size: 1.3rem;
}
header .jumbotron hr {
	border-color: initial;
}
header .jumbotron .lead .btn {
	width: 175px;
}
header .jumbotron .lead .btn-left {
	margin-right: 20px;
}
header .jumbotron .lead .btn span {
	display: inline-block;
	height: 40px;
}
header .jumbotron .lead .btn span span {
	vertical-align : middle;
}
header .jumbotron .lead .text-muted {
	font-size: 14px;
	padding-top: 10px;
}
header #carousel {
	background-color: #f1f1f1;
	border: 2px solid #444;
	color: #000;
	margin-top: 64px;
	margin-bottom: 64px;
}
header .carousel-item {
	height:300px;
	vertical-align: middle;
}
header .carousel-caption,
header .carousel-control {
	color: #000;
	text-shadow: none;
}
header .carousel-indicators li {
	border: 1px solid #000;
}
header .carousel-indicators .active {
	background-color: #000;
}
header #carousel .highlight,
header #carousel .highlight pre {
	background-color: transparent;
	border: none;
}
@media (max-width: 33em) {
	header .jumbotron h1.display-2{
		font-size: 4.5rem;
	}
	header .jumbotron .lead .btn {
		margin-bottom: 20px;
	}
}
@media (max-width: 61em) {
  header #carousel {
    margin-top: 0px;
  }
}

/* feature */
#feature h2 {
	font-size: 42px;
	letter-spacing: 4px;
	padding-top: 60px;
	text-align: center;
}
#feature h3 {
	letter-spacing: 1px;
	font-size: 16px;
	text-decoration: underline;
}
#feature .block-code {
	min-height: 500px;
}
#feature .btn {
	margin-top: 40px;
}

@media (min-width: 62em) {
	#feature .row .col-lg-6:first-child {
		padding-right: 45px;
	}
	#feature .row .col-lg-6:last-child {
		padding-left: 45px;
	}
}


/* pricing */
#pricing .table thead th {
	text-align: center;
}
#pricing .table td {
	text-align: center;
}
#pricing .fa-times {
	color: #c9302c;
}
#pricing .fa-check-square-o {
	color: rgb(68, 157, 68);
}

/* support */
#support {
	text-align: center;
}
#support h2 {
	padding-bottom: 20px;
}
#support .card {
	border: 0.0625rem solid #ccc;
}
#support .card-text {
	min-height: 75px;
}
#support i {
	color: #0275d8;
	padding-bottom: 20px;
}

/* product */
#product .product-section {
	letter-spacing: 1px;
	font-weight: bold;
	padding-bottom: 5px;
}
#product ul {
	list-style: none;
	padding-left: 0px;
}
#product a {
	color: #999;
	font-size: 14px;
	letter-spacing: 1px;
}
#product a:hover {
	color: #f1f1f1;
	text-decoration: none;
}

/* footer */
footer hr {
	border-color: #666;
	margin-left: 20px;
	margin-right: 20px;
}
footer a {
	color: #666;
	text-decoration: none;
}
footer a:hover {
	color: #666;
	opacity: 0.7;
    transition: all 0.4s ease-in-out 0s;
	text-decoration: none;
}
footer .social a {
	font-size: 24px;
	padding-left: 10px;
	padding-right: 10px;
}
@media (max-width: 61em) {
  footer {
	padding: 20px 0;
  }
}
</style>

<style>
</style>
