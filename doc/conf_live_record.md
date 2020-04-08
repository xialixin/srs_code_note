<html>

<head>
<meta http-equiv=Content-Type content="text/html; charset=gb2312">
<meta name=Generator content="Microsoft Word 15 (filtered)">
<title>会议录像与直播重构方案设计</title>
<style>
<!--
 /* Font Definitions */
 @font-face
	{font-family:宋体;
	panose-1:2 1 6 0 3 1 1 1 1 1;}
@font-face
	{font-family:"Cambria Math";
	panose-1:2 4 5 3 5 4 6 3 2 4;}
@font-face
	{font-family:等线;
	panose-1:2 1 6 0 3 1 1 1 1 1;}
@font-face
	{font-family:"等线 Light";
	panose-1:2 1 6 0 3 1 1 1 1 1;}
@font-face
	{font-family:新宋体;
	panose-1:2 1 6 9 3 1 1 1 1 1;}
@font-face
	{font-family:"\@等线";
	panose-1:2 1 6 0 3 1 1 1 1 1;}
@font-face
	{font-family:"\@等线 Light";
	panose-1:2 1 6 0 3 1 1 1 1 1;}
@font-face
	{font-family:"\@新宋体";
	panose-1:2 1 6 9 3 1 1 1 1 1;}
@font-face
	{font-family:"\@宋体";
	panose-1:2 1 6 0 3 1 1 1 1 1;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{margin:0cm;
	margin-bottom:.0001pt;
	text-align:justify;
	text-justify:inter-ideograph;
	font-size:10.5pt;
	font-family:等线;}
h1
	{mso-style-link:"标题 1 字符";
	margin-top:17.0pt;
	margin-right:0cm;
	margin-bottom:16.5pt;
	margin-left:0cm;
	text-align:justify;
	text-justify:inter-ideograph;
	line-height:240%;
	page-break-after:avoid;
	font-size:22.0pt;
	font-family:等线;}
h2
	{mso-style-link:"标题 2 字符";
	margin-top:13.0pt;
	margin-right:0cm;
	margin-bottom:13.0pt;
	margin-left:0cm;
	text-align:justify;
	text-justify:inter-ideograph;
	line-height:173%;
	page-break-after:avoid;
	font-size:16.0pt;
	font-family:"等线 Light";}
h3
	{mso-style-link:"标题 3 字符";
	margin-top:13.0pt;
	margin-right:0cm;
	margin-bottom:13.0pt;
	margin-left:0cm;
	text-align:justify;
	text-justify:inter-ideograph;
	line-height:173%;
	page-break-after:avoid;
	font-size:16.0pt;
	font-family:等线;}
h4
	{mso-style-link:"标题 4 字符";
	margin-top:14.0pt;
	margin-right:0cm;
	margin-bottom:14.5pt;
	margin-left:0cm;
	text-align:justify;
	text-justify:inter-ideograph;
	line-height:156%;
	page-break-after:avoid;
	font-size:14.0pt;
	font-family:"等线 Light";}
p.MsoToc1, li.MsoToc1, div.MsoToc1
	{margin:0cm;
	margin-bottom:.0001pt;
	text-align:justify;
	text-justify:inter-ideograph;
	font-size:10.5pt;
	font-family:等线;}
p.MsoToc2, li.MsoToc2, div.MsoToc2
	{margin-top:0cm;
	margin-right:0cm;
	margin-bottom:0cm;
	margin-left:21.0pt;
	margin-bottom:.0001pt;
	text-align:justify;
	text-justify:inter-ideograph;
	font-size:10.5pt;
	font-family:等线;}
p.MsoToc3, li.MsoToc3, div.MsoToc3
	{margin-top:0cm;
	margin-right:0cm;
	margin-bottom:0cm;
	margin-left:42.0pt;
	margin-bottom:.0001pt;
	text-align:justify;
	text-justify:inter-ideograph;
	font-size:10.5pt;
	font-family:等线;}
p.MsoHeader, li.MsoHeader, div.MsoHeader
	{mso-style-link:"页眉 字符";
	margin:0cm;
	margin-bottom:.0001pt;
	text-align:center;
	layout-grid-mode:char;
	border:none;
	padding:0cm;
	font-size:9.0pt;
	font-family:等线;}
p.MsoFooter, li.MsoFooter, div.MsoFooter
	{mso-style-link:"页脚 字符";
	margin:0cm;
	margin-bottom:.0001pt;
	layout-grid-mode:char;
	font-size:9.0pt;
	font-family:等线;}
a:link, span.MsoHyperlink
	{color:#0563C1;
	text-decoration:underline;}
a:visited, span.MsoHyperlinkFollowed
	{color:#954F72;
	text-decoration:underline;}
p.MsoNoSpacing, li.MsoNoSpacing, div.MsoNoSpacing
	{mso-style-link:"无间隔 字符";
	margin:0cm;
	margin-bottom:.0001pt;
	font-size:11.0pt;
	font-family:等线;}
p.MsoListParagraph, li.MsoListParagraph, div.MsoListParagraph
	{margin:0cm;
	margin-bottom:.0001pt;
	text-align:justify;
	text-justify:inter-ideograph;
	text-indent:21.0pt;
	font-size:10.5pt;
	font-family:等线;}
p.MsoTocHeading, li.MsoTocHeading, div.MsoTocHeading
	{margin-top:12.0pt;
	margin-right:0cm;
	margin-bottom:0cm;
	margin-left:0cm;
	margin-bottom:.0001pt;
	line-height:107%;
	page-break-after:avoid;
	font-size:16.0pt;
	font-family:"等线 Light";
	color:#2F5496;}
span.1
	{mso-style-name:"标题 1 字符";
	mso-style-link:"标题 1";
	font-weight:bold;}
span.2
	{mso-style-name:"标题 2 字符";
	mso-style-link:"标题 2";
	font-family:"等线 Light";
	font-weight:bold;}
span.a
	{mso-style-name:"页眉 字符";
	mso-style-link:页眉;}
span.a0
	{mso-style-name:"页脚 字符";
	mso-style-link:页脚;}
span.3
	{mso-style-name:"标题 3 字符";
	mso-style-link:"标题 3";
	font-weight:bold;}
span.4
	{mso-style-name:"标题 4 字符";
	mso-style-link:"标题 4";
	font-family:"等线 Light";
	font-weight:bold;}
span.a1
	{mso-style-name:"无间隔 字符";
	mso-style-link:无间隔;}
span.Char
	{mso-style-name:"无间隔 Char";}
.MsoChpDefault
	{font-family:等线;}
 /* Page Definitions */
 @page WordSection1
	{size:595.3pt 841.9pt;
	margin:72.0pt 90.0pt 72.0pt 90.0pt;
	layout-grid:15.6pt;}
div.WordSection1
	{page:WordSection1;}
 /* List Definitions */
 ol
	{margin-bottom:0cm;}
ul
	{margin-bottom:0cm;}
-->
</style>

</head>

<body lang=ZH-CN link="#0563C1" vlink="#954F72" style='text-justify-trim:punctuation'>

<div class=WordSection1 style='layout-grid:15.6pt'><b><span lang=EN-US
style='font-size:22.0pt;line-height:240%;font-family:等线'><br clear=all
style='page-break-before:always'>
</span></b>

<h1><a name="_Toc37241775">会议直播与录相方案设计</a></h1>

<p class=MsoNormal align=left style='text-align:left'><b><span lang=EN-US
style='font-size:22.0pt'>&nbsp;</span></b></p>

<p class=MsoTocHeading>目录</p>

<p class=MsoToc1><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241775"><span lang=EN-US><span lang=EN-US>会议直播与录相方案设计</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc1><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241776"><span lang=EN-US><span lang=EN-US>需求</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc1><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241777"><span lang=EN-US><span lang=EN-US>产品功能</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc2><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241778"><span lang=EN-US><span lang=EN-US>功能性需求</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241779"><span lang=EN-US><span lang=EN-US>会议直播</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241780"><span lang=EN-US><span lang=EN-US>会议录像</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc2><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241781"><span lang=EN-US><span lang=EN-US>非功能性需求</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc1><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241782"><span lang=EN-US><span lang=EN-US>产品使用场景</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc1><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241783"><span lang=EN-US><span lang=EN-US>系统设计</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc2><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241784"><span lang=EN-US><span lang=EN-US>架构设计</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241785"><span lang=EN-US><span lang=EN-US>会议总体架构(</span></span><span
lang=EN-US><span lang=EN-US>非集群)</span></span><span style='color:windowtext;
display:none;text-decoration:none'> </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc2><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241786"><span lang=EN-US><span lang=EN-US>功能模块设计</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241787">MCS<span lang=EN-US><span lang=EN-US>的内部结构</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241788">RCS<span lang=EN-US><span lang=EN-US>与MLG</span></span><span
lang=EN-US><span lang=EN-US>内部结构</span></span><span style='color:windowtext;
display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc2><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241789"><span lang=EN-US><span lang=EN-US>模块消息交互与流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241790"><span lang=EN-US><span lang=EN-US>会议录像基本流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241791"><span lang=EN-US><span lang=EN-US>会议直播基本流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241792"><span lang=EN-US><span lang=EN-US>同时开始录像与直播流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241793"><span lang=EN-US><span lang=EN-US>同时直播与录像时，先停止直播流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241794"><span lang=EN-US><span lang=EN-US>在已有直播上切换屏幕共享直播流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241795"><span lang=EN-US><span lang=EN-US>直接开启屏幕共享直播流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241796"><span lang=EN-US><span lang=EN-US>一个会议同时有两个或以上直播或录像流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241797"><span lang=EN-US><span lang=EN-US>多人自动模式添加，删除成员流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241798"><span lang=EN-US><span lang=EN-US>多人自动模式手动模式切换流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241799"><span lang=EN-US><span lang=EN-US>第三方会议接入流程</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc2><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241800"><span lang=EN-US><span lang=EN-US>数据结构设计</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241801"><span lang=EN-US><span lang=EN-US>会议录像与直播实体关联图</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241802"><span lang=EN-US><span lang=EN-US>会议实体信息</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241803"><span lang=EN-US><span lang=EN-US>会议成员信息</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241804"><span lang=EN-US><span lang=EN-US>录像会话</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241805"><span lang=EN-US><span lang=EN-US>录像文件列表</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc3><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241806"><span lang=EN-US><span lang=EN-US>直播会话</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc1><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241807"><span lang=EN-US><span lang=EN-US>系统测试</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoToc2><span class=MsoHyperlink><span lang=EN-US><a
href="#_Toc37241808"><span lang=EN-US><span lang=EN-US>测试用例</span></span><span
style='color:windowtext;display:none;text-decoration:none'>... </span><span
style='color:windowtext;display:none;text-decoration:none'>0</span></a></span></span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal align=left style='text-align:left'><b><span lang=EN-US
style='font-size:22.0pt'>&nbsp;</span></b></p>

<p class=MsoNormal align=left style='text-align:left'><b><span lang=EN-US
style='font-size:22.0pt'>&nbsp;</span></b></p>

<p class=MsoNormal align=left style='text-align:left'><b><span lang=EN-US
style='font-size:22.0pt'>&nbsp;</span></b></p>

<h1><a name="_Toc37241776">需求</a></h1>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
font-family:新宋体'>在使用实时音视频的过程中，经常会有两种情况，一是需要将音视频通话，会议的全过程录像，方便过后回看以及相应处理。如重要会议需要事后回看学习，等等<span
lang=EN-US>;</span>另外一种是通话或会议时，需要将全过程对外发布，让更多不在现场的人在第一时间能了解到会议实时情况，所以需要将其广播出去。也就是将会议直播出去。如在线教育，直播连麦等等。</span></p>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
font-family:新宋体'>从上面的需求可以归类成两个最基本功能，就是会议录像与直播，针对这两个功能，在一些现实中会在这两个基本需求的基础上，来满足不同应用场景。为了让系统能很好适应这些些场景，下面从功能性或非功能性方面详细细化这两大基础功能。</span></p>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
font-family:新宋体'>我们会议系统现在部分功能都已经实现，但随着业务，应用场景的不段变化，现在方案实现，越来越复杂，有新需求变更时，实现也越来越来麻烦。为了解决目前这些问题，需要对会议直播与录像进行重构，以更好方式来完成已有业务功能，以及更容易适应新的需求变更。</span></p>

<h1><a name="_Toc37241777">产品功能</a></h1>

<h2><a name="_Toc37241778">功能性需求</a></h2>

<table class=MsoTable15Grid4Accent5 border=1 cellspacing=0 cellpadding=0
 width=491 style='width:368.3pt;border-collapse:collapse;border:none'>
 <tr style='height:14.25pt'>
  <td width=96 nowrap valign=top style='width:72.0pt;border:solid #5B9BD5 1.0pt;
  border-right:none;background:#5B9BD5;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>功能顶</span></b></p>
  </td>
  <td width=225 nowrap valign=top style='width:168.75pt;border-top:solid #5B9BD5 1.0pt;
  border-left:none;border-bottom:solid #5B9BD5 1.0pt;border-right:none;
  background:#5B9BD5;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>功能点</span></b></p>
  </td>
  <td width=83 nowrap colspan=2 valign=top style='width:62.25pt;border-top:
  solid #5B9BD5 1.0pt;border-left:none;border-bottom:solid #5B9BD5 1.0pt;
  border-right:none;background:#5B9BD5;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>功能级别</span></b></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border:solid #5B9BD5 1.0pt;
  border-left:none;background:#5B9BD5;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>选顶</span></b></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=96 nowrap rowspan=8 valign=top style='width:72.0pt;border:solid #9CC2E5 1.0pt;
  border-top:none;background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播</span></p>
  </td>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>多人单人直播</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:42.75pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:42.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同会议可输出多个直播</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:42.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:42.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:36.75pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:36.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>屏幕共享直播</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:36.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:36.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>输出布局指定</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:23.25pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:23.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>直播启停控制</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:23.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:23.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:19.5pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:19.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>人离开画面，暂停直播</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:19.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>低</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:19.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>可选 </span></p>
  </td>
 </tr>
 <tr style='height:19.5pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:19.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>两个会议主播混屏</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:19.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>低</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:19.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>可选 </span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>只输出音频或视频</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=96 nowrap rowspan=5 valign=top style='width:72.0pt;border:solid #9CC2E5 1.0pt;
  border-top:none;background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议录像</span></p>
  </td>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>支持以上会议直播同样功能</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像文件支持<span lang=EN-US>mp4,flv</span>等</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>支持录像<span lang=EN-US>h264</span>祼流与<span lang=EN-US>aac</span>祼流文件</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>中</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>可选</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像能指定输出的分辨率大小等</span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>中</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:17.2pt'>
  <td width=236 nowrap colspan=2 valign=top style='width:177.0pt;border-top:
  none;border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:17.2pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>支持截图<span lang=EN-US>jpg</span></span></p>
  </td>
  <td width=72 nowrap valign=top style='width:54.0pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:17.2pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>中</span></p>
  </td>
  <td width=87 nowrap valign=top style='width:65.3pt;border-top:none;
  border-left:none;border-bottom:solid #9CC2E5 1.0pt;border-right:solid #9CC2E5 1.0pt;
  background:#DEEAF6;padding:0cm 5.4pt 0cm 5.4pt;height:17.2pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>可选</span></p>
  </td>
 </tr>
 <tr height=0>
  <td width=96 style='border:none'></td>
  <td width=225 style='border:none'></td>
  <td width=11 style='border:none'></td>
  <td width=72 style='border:none'></td>
  <td width=87 style='border:none'></td>
 </tr>
</table>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>&nbsp;</span></p>

<h3><a name="_Toc37241779">会议直播</a></h3>

<h4>多人单人直播</h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
font-family:宋体;color:black'>可以把会议的单人成员的音视频输出直播，多人混屏输出直播</span></p>

<h4>同会议可输出多个直播</h4>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span><span
style='font-size:14.0pt;font-family:宋体;color:black'>同会议所有成员，可以任一组合，输出到多个直播，也就是多对一，如会议成员<span
lang=EN-US>1,2,3 4&nbsp;&nbsp; </span>如<span lang=EN-US>1</span>，<span
lang=EN-US>2</span>输出直播频道<span lang=EN-US>1</span>， 【<span lang=EN-US>2</span>，<span
lang=EN-US>3</span>】输出到直播<span lang=EN-US>2 </span>， 【<span lang=EN-US>1</span>，<span
lang=EN-US>2</span>，<span lang=EN-US>3</span>，<span lang=EN-US>4</span>】输出到直播<span
lang=EN-US>3</span></span></p>

<h4>屏幕共享直播</h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
font-family:新宋体;color:black'>每个成员都可以有屏幕共享输出，需要确定会议的成员视频与该成员的共享屏幕是否同时输出<span
lang=EN-US>, </span>屏幕共享与成员视频，可指定任一输出，还是二者都可以</span></p>

<h4>输出布局指定</h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
font-family:新宋体;color:black'>输出时可以指定屏幕的布局，需要确定最大人数，也需要考虑横屏与竖屏，剪栽模式，画面黑边处理</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<h4>直播启停控制</h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
font-family:新宋体;color:black'>会议在直播中，每个成员加入或退出需要自动加入或退出直播，所有人退出，自动停止所有直播</span></p>

<h4>人离开画面，暂停直播</h4>

<p class=MsoNormal style='text-indent:22.0pt'><span style='font-size:11.0pt;
color:black'>会议直播中，画面中人离开，需要自动停止直播，该功能需要依赖<span lang=EN-US>AI</span>目标检查功能</span></p>

<h4>两个会议主播混屏</h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
color:black'>旁路直播中，两个主播<span lang=EN-US>pk</span>画面</span></p>

<h4>只输出音频或视频</h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
color:black'>只输出音频或视频</span></p>

<h3><a name="_Toc37241780">会议录像</a></h3>

<h4>录像文件支持<span lang=EN-US>mp4,flv</span></h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
color:black'>录像支持<span lang=EN-US>flv</span>与<span lang=EN-US>mp4, </span>需要考虑单个会议文件的时长，是否需要考虑分割成多个文件</span></p>

<h4>支持录像<span lang=EN-US>h264</span>祼流与<span lang=EN-US>aac</span>祼流文件</h4>

<p class=MsoNormal style='text-indent:28.0pt'><span style='font-size:14.0pt;
color:black'>可以将输出单独录像成<span lang=EN-US>h264,aac</span>祼流</span></p>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>&nbsp;</span></p>

<h2><a name="_Toc37241781">非功能性需求</a></h2>

<table class=MsoTable15Grid4Accent1 border=1 cellspacing=0 cellpadding=0
 width=509 style='width:382.0pt;border-collapse:collapse;border:none'>
 <tr style='height:14.25pt'>
  <td width=96 nowrap valign=top style='width:72.0pt;border:solid #4472C4 1.0pt;
  border-right:none;background:#4472C4;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>功能顶</span></b></p>
  </td>
  <td width=236 nowrap valign=top style='width:177.0pt;border-top:solid #4472C4 1.0pt;
  border-left:none;border-bottom:solid #4472C4 1.0pt;border-right:none;
  background:#4472C4;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>功能点</span></b></p>
  </td>
  <td width=83 nowrap valign=top style='width:62.6pt;border-top:solid #4472C4 1.0pt;
  border-left:none;border-bottom:solid #4472C4 1.0pt;border-right:none;
  background:#4472C4;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>功能级别</span></b></p>
  </td>
  <td width=94 nowrap valign=top style='width:70.4pt;border:solid #4472C4 1.0pt;
  border-left:none;background:#4472C4;padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>选顶</span></b></p>
  </td>
 </tr>
 <tr style='height:35.25pt'>
  <td width=96 rowspan=3 valign=top style='width:72.0pt;border:solid #8EAADB 1.0pt;
  border-top:none;background:#D9E2F3;padding:0cm 5.4pt 0cm 5.4pt;height:35.25pt'>
  <p class=MsoNormal align=center style='text-align:center'><b><span
  style='font-size:11.0pt;color:black'>会议录像与直播</span></b></p>
  </td>
  <td width=236 valign=top style='width:177.0pt;border-top:none;border-left:
  none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  background:#D9E2F3;padding:0cm 5.4pt 0cm 5.4pt;height:35.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span lang=EN-US
  style='font-size:11.0pt;color:black'>1.</span><span style='font-size:11.0pt;
  color:black'>一个会议最大支持人数，会议直播与录像的输入，输出数</span></p>
  </td>
  <td width=83 nowrap valign=top style='width:62.6pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  background:#D9E2F3;padding:0cm 5.4pt 0cm 5.4pt;height:35.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=94 nowrap valign=top style='width:70.4pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  background:#D9E2F3;padding:0cm 5.4pt 0cm 5.4pt;height:35.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:20.25pt'>
  <td width=236 nowrap valign=top style='width:177.0pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:20.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span lang=EN-US
  style='font-size:11.0pt;color:black'>2.</span><span style='font-size:11.0pt;
  color:black'>会议直播的最大延迟</span></p>
  </td>
  <td width=83 nowrap valign=top style='width:62.6pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:20.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=94 nowrap valign=top style='width:70.4pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:20.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
 <tr style='height:21.75pt'>
  <td width=236 nowrap valign=top style='width:177.0pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  background:#D9E2F3;padding:0cm 5.4pt 0cm 5.4pt;height:21.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span lang=EN-US
  style='font-size:11.0pt;color:black'>3.</span><span style='font-size:11.0pt;
  color:black'>录像与直播画面的连续性</span></p>
  </td>
  <td width=83 nowrap valign=top style='width:62.6pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  background:#D9E2F3;padding:0cm 5.4pt 0cm 5.4pt;height:21.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>高</span></p>
  </td>
  <td width=94 nowrap valign=top style='width:70.4pt;border-top:none;
  border-left:none;border-bottom:solid #8EAADB 1.0pt;border-right:solid #8EAADB 1.0pt;
  background:#D9E2F3;padding:0cm 5.4pt 0cm 5.4pt;height:21.75pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>必选</span></p>
  </td>
 </tr>
</table>

<p class=MsoNormal><span lang=EN-US style='font-size:11.0pt;color:black'>&nbsp;</span></p>

<p class=MsoNormal><b><span lang=EN-US style='font-size:14.0pt;color:black'>1.</span></b><b><span
style='font-size:14.0pt;color:black'>一个会议最大支持人数，会议直播与录像的输入，输出数</span></b></p>

<p class=MsoNormal style='text-indent:21.0pt'><span style='font-size:14.0pt'>会议人数，是指与参加会议的实际人数<span
lang=EN-US>; </span>输入数是指需要录像或直播的人数，输出数是</span></p>

<p class=MsoNormal style='text-indent:21.0pt'><span style='font-size:14.0pt'>向直播推流的频道数与录像输出的个数之后</span></p>

<p class=MsoNormal><b><span lang=EN-US style='font-size:14.0pt'>2.</span></b><b><span
lang=EN-US style='font-size:14.0pt;color:black'> </span></b><b><span
style='font-size:14.0pt;color:black'>会议直播的最大延迟</span></b></p>

<p class=MsoNormal><span lang=EN-US style='font-size:14.0pt;color:black'>&nbsp;&nbsp;&nbsp;
</span><span style='font-size:14.0pt;color:black'>会议的视频与直播后的视频最大允许的延迟</span></p>

<p class=MsoNormal><b><span lang=EN-US style='font-size:14.0pt'>3.</span></b><b><span
lang=EN-US style='font-size:14.0pt;color:black'> </span></b><b><span
style='font-size:14.0pt;color:black'>录像与直播画面的连续性</span></b></p>

<p class=MsoNormal><b><span lang=EN-US style='font-size:14.0pt'>&nbsp;&nbsp; </span></b><span
lang=EN-US style='font-size:14.0pt'>&nbsp;</span><span style='font-size:14.0pt'>画面花屏，或卡顿的次数，在直播或录像过程有可能网络掉线后马上恢复</span></p>

<h1><a name="_Toc37241782">产品使用场景</a></h1>

<table class=MsoNormalTable border=0 cellspacing=0 cellpadding=0 width=575
 style='width:431.0pt;border-collapse:collapse'>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>创建会议，开始直播，中间有人加入会议，有人退出会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>创建会议，多人在开会中，现在还没有直播，在某个时候，需要开始直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>会议还没有开始，尝试开启直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>会议开始后，想看某人的直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>5.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>会议开始后，想看多人的混屏直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>6.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>想看某人的共享屏幕，同时想看该人的成员视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>7.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>想把直播输出的画面，同时也能回看录像</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>8.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>我现在正在看共享屏幕，突然我想看成员的视频， 反之，也一样</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>9.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp; </span></span><span
  style='font-size:14.0pt;color:black'>我想看多人的的共享屏幕</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>10.</span><span style='font-size:14.0pt;color:black'>我只需要会议中某人的音频或视频，</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>11.</span><span style='font-size:14.0pt;color:black'>我需要会议中某画面中的图片文件</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>12.</span><span style='font-size:14.0pt;color:black'>我想在某个时候开始直播与录像</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>13.</span><span style='font-size:14.0pt;color:black'>会议结束后，我要看该会议所有录像，包括个人，多个，屏幕共享等等</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>14.</span><span style='font-size:14.0pt;color:black'>该会议是永久会议，这次结束后，下次开始时，我需要自动录像与直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>15.</span><span style='font-size:14.0pt;color:black'>我用手机看多人会议直播，画面需要根据手机屏幕自适应</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>16.</span><span style='font-size:14.0pt;color:black'>会议直播过程，与会的终端突然没有音视频流，可以网络断线等等</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>17.</span><span style='font-size:14.0pt;color:black'>会议直播中， 终端禁止音频，视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>18.</span><span style='font-size:14.0pt;color:black'>会议直播中，频繁退出加入会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>19.</span><span style='font-size:14.0pt;color:black'>会议直播中，切换前后摄象头</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>20.</span><span style='font-size:14.0pt;color:black'>会议直播中，开启共享屏幕</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>21.</span><span style='font-size:14.0pt;color:black'>会议直播中，会议加入人数到达最大数怎么样</span></p>
  </td>
 </tr>
 <tr style='height:5.95pt'>
  <td width=575 nowrap valign=bottom style='width:431.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:5.95pt'>
  <p class=MsoListParagraph align=left style='margin-left:18.0pt;text-align:
  left;text-indent:-18.0pt'><span lang=EN-US style='font-size:14.0pt;
  color:black'>22.</span><span style='font-size:14.0pt;color:black'>会议直播中，突然一下加入多个人，或退出多人</span></p>
  </td>
 </tr>
</table>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<h1><a name="_Toc37241783">系统设计</a></h1>

<h2><a name="_Toc37241784">架构设计</a></h2>

<h3><a name="_Toc37241785">会议总体架构<span lang=EN-US>(</span>非集群<span lang=EN-US>)</span></a></h3>

<p class=MsoNormal><span lang=EN-US><img width=937 height=510
src="conf_live_record.files/image001.png"></span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<h2><a name="_Toc37241786">功能模块设计</a></h2>

<h3><a name="_Toc37241787"><span lang=EN-US>MCS</span>的内部结构</a></h3>

<p class=MsoNormal><span lang=EN-US>Mcs</span>是媒体系统的总的控制中心，下图只例出与会议直播与录像相关的模块结构</p>

<p class=MsoNormal><span lang=EN-US><img width=912 height=345
src="conf_live_record.files/image002.png"></span></p>

<h3><a name="_Toc37241788"><span lang=EN-US>RCS</span>与<span lang=EN-US>MLG</span>内部结构</a></h3>

<h4><span lang=EN-US>MLG</span>内部结构</h4>

<p class=MsoNormal><span lang=EN-US><img width=907 height=652
src="conf_live_record.files/image003.png"></span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<h4><span lang=EN-US>RCS</span>内部结构</h4>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US><img width=919 height=519
src="conf_live_record.files/image004.png"></span></p>

<h2><a name="_Toc37241789">模块消息交互与流程</a></h2>

<h3><a name="_Toc37241790">会议录像基本流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>首先主持人打开<span lang=EN-US>app,</span>登录会议系统，并创建会议准备开会</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>主持人开会，通过<span lang=EN-US>RestServer,CCM,
CallRouteGW,MCS</span>，创建会议，媒体通道等资源信息基中包括<span lang=EN-US>mas</span>的对外地址，端口等，同时通过<span
lang=EN-US>mcs</span>开启会议录像</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>客户端获取媒体通道等信息后，向指定的地址与端口发送音视频媒体流</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>开启会议录像过程<span lang=EN-US>:</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>5.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>首先<span lang=EN-US>mcs</span>向<span
lang=EN-US>rcs</span>获取接收媒体信息，包括音频与视频接收端口</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>6.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>请求<span lang=EN-US>mps</span>创建一个通道，将混音媒体流发送到<span
lang=EN-US>rcs</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>7.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>请求<span lang=EN-US>mcu</span>创建一个房间，同时通知<span
lang=EN-US>mas</span>将成员的视频流发送到<span lang=EN-US>mcu, </span>通知<span lang=EN-US>mcu</span>将<span
lang=EN-US>mcu</span>混屏后的流发送到<span lang=EN-US>rcs</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>8.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Rcs</span><span
style='font-size:14.0pt'>收到<span lang=EN-US>mcu</span>的视频，<span lang=EN-US>mps</span>的音频后，
将视频保存成<span lang=EN-US>h264, </span>音视保存<span lang=EN-US>aac, </span>同时将音视频复合后，生成<span
lang=EN-US>flv</span>或<span lang=EN-US>mp4</span>文件，保存在磁盘上</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>9.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>主持人会议结束，在<span lang=EN-US>app</span>结束会议，通过<span
lang=EN-US>RestServer,CCM, CallRouteGW,MCS</span>删除相关通道，释放相关资源，同时通过<span
lang=EN-US>mcs</span>停止会议录像</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>10.</span><span lang=EN-US
style='font-size:14.0pt'>Mcs</span><span style='font-size:14.0pt'>停止会议录像过程：</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>11.</span><span lang=EN-US
style='font-size:14.0pt'>Mcs</span><span style='font-size:14.0pt'>请求<span
lang=EN-US>mps</span>停止向<span lang=EN-US>rcs</span>发送音频数据，同时删除相关通道</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>12.</span><span lang=EN-US
style='font-size:14.0pt'>Mcs</span><span style='font-size:14.0pt'>请求<span
lang=EN-US>mas</span>停止向<span lang=EN-US>mcu</span>发送相关视频数据，同时通知<span
lang=EN-US>mcu</span>通知向<span lang=EN-US>rcs</span>发送视频数据，在<span lang=EN-US>mcu</span>中释放会议房间的所有资源</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>13.</span><span lang=EN-US
style='font-size:14.0pt'>RCS</span><span style='font-size:14.0pt'>停止写录像文件，生成会议录像列表</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>14.</span><span style='font-size:14.0pt'>录像点播过程：</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>15.</span><span style='font-size:14.0pt'>客户端通过<span
lang=EN-US>RESTServer, CCM, MCS</span>根据会议号，时间范围，获取会议列表，得到相关会议录像的点播<span
lang=EN-US>url</span>。</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>16.</span><span style='font-size:14.0pt'>客户端通过点播<span
lang=EN-US>url</span>，打开录像视频回看</span></p>

<h4>开会与停止会议流程<span lang=EN-US>:</span></h4>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US><img width=884 height=838
src="conf_live_record.files/image005.png"></span></p>

<h4>启停录像流程</h4>

<p class=MsoNormal><span lang=EN-US><img width=1003 height=991
src="conf_live_record.files/image006.png"></span></p>

<h3><a name="_Toc37241791">会议直播基本流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>首先主持人打开<span lang=EN-US>app,</span>登录会议系统，并创建会议准备开会</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>主持人开会，通过<span lang=EN-US>RestServer,CCM,
CallRouteGW,MCS</span>，创建会议，媒体通道等资源信息基中包括<span lang=EN-US>mas</span>的对外地址，端口等 &nbsp;</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>客户端获取媒体通道等信息后，向指定的地址与端口发送音视频媒体流，会议开始</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>开启会议直播过程<span lang=EN-US>:</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>5.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>主持人或其他人员，选择会议，并发送开始直播命令</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>6.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>收到开始直播命令后，向<span lang=EN-US>mlg</span>获取接收媒体信息，包括音频与视频接收端口</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>7.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>请求<span lang=EN-US>mps</span>创建一个通道，将混音媒体流发送到<span
lang=EN-US>mlg</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>8.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>请求<span lang=EN-US>mcu</span>创建一个房间，同时通知<span
lang=EN-US>mas</span>将成员的视频流发送到<span lang=EN-US>mcu, </span>通知<span lang=EN-US>mcu</span>将<span
lang=EN-US>mcu</span>混屏后的流发送到<span lang=EN-US>mlg</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>9.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>mlg</span><span
style='font-size:14.0pt'>收到<span lang=EN-US>mcu</span>的视频，<span lang=EN-US>mps</span>的音频后，将音视频复合后封装<span
lang=EN-US>flv</span>后通过<span lang=EN-US>rtmp</span>发送到直播服务器</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>10.</span><span style='font-size:14.0pt'>主持人会议结束时，在
<span lang=EN-US>app</span>结束会议，通过<span lang=EN-US>RestServer,CCM,
CallRouteGW,MCS</span>删除相关通道，释放相关资源，同时通过<span lang=EN-US>mcs</span>停止会议录像</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>11.</span><span lang=EN-US
style='font-size:14.0pt'>Mcs</span><span style='font-size:14.0pt'>停止会议录像过程：</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>12.</span><span lang=EN-US
style='font-size:14.0pt'>Mcs</span><span style='font-size:14.0pt'>请求<span
lang=EN-US>mps</span>停止向<span lang=EN-US>mlg</span>发送音频数据，同时删除相关通道</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>13.</span><span lang=EN-US
style='font-size:14.0pt'>Mcs</span><span style='font-size:14.0pt'>请求<span
lang=EN-US>mas</span>停止向<span lang=EN-US>mcu</span>发送相关视频数据，同时通知<span
lang=EN-US>mcu</span>通知向<span lang=EN-US>mlg</span>发送视频数据，在<span lang=EN-US>mcu</span>中释放会议房间的所有资源</span></p>

<h4>启停直播流程</h4>

<p class=MsoNormal><span lang=EN-US><img width=1055 height=950
src="conf_live_record.files/image007.png"></span></p>

<h3><a name="_Toc37241792">同时开始录像与直播流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>会议先开始录像流程， 录像开始</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>向会议发送开始直播命令</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>收到直播命令，向<span lang=EN-US>mlg</span>获取媒体端口等资源，同时向直播系统申请直播推流地址，</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:0cm'><span
style='font-size:14.0pt'>直播地址可以是内网地址，这个可以通过参数配置</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>根据本次直播请求生成一个新的<span lang=EN-US>ssrc,
ssrc</span>在本次直播中是唯一的</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>5.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>根据<span lang=EN-US>ssrc</span>向<span
lang=EN-US>mps</span>创建一个新的通道，同时通知<span lang=EN-US>mps</span>向<span lang=EN-US>mlg</span>发送混音流</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>6.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs </span><span
style='font-size:14.0pt'>向<span lang=EN-US>mcu</span>发送创建房间命令，如果<span
lang=EN-US>mcu</span>返回已存在，跳过，否则创建一个新的房间</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>7.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>通知<span lang=EN-US>mas</span>，需要将哪些人的视频发送到<span
lang=EN-US>mcu, </span>可以所有人或指定某些人</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>8.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>通知<span lang=EN-US>mcu </span>创建一个<span lang=EN-US>observer,
</span>混流指定视频，输出到<span lang=EN-US>mlg</span>视频端口</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>9.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mlg</span><span
style='font-size:14.0pt'>收到<span lang=EN-US>mps</span>的音频与<span lang=EN-US>mcu</span>的视频后，封装成<span
lang=EN-US>rtmp</span>流，发送到直播系统</span></p>

<h3><a name="_Toc37241793">同时直播与录像时，先停止直播流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>系统当前一个会议有一个录像与直播</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>首先向<span lang=EN-US>mcs</span>发送停止直播命令</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>收到停止直播命令后，向<span lang=EN-US>mlg</span>发送停止通知，<span
lang=EN-US>mlg</span>停止向直播服务器推流。</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>通知<span lang=EN-US>mps,</span>删除该直播的音频通道</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>5.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>通知<span lang=EN-US>mcu</span>删除该直播的<span lang=EN-US>observer</span></span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<h3><a name="_Toc37241794">在已有直播上切换屏幕共享直播流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>首先开启会议直播，默认是成员视频</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>通过本次直播<span lang=EN-US>sessionId, </span>发送切换成员命令，成员列表带共享屏幕类型</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>收到命令，检查成员列表，哪些是屏幕视频，哪些是成员视频，分别通知到<span lang=EN-US>mas</span>，将相关媒体发送到<span
lang=EN-US>mcu</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>根据成员列表，重置<span lang=EN-US>mcu</span>的<span
lang=EN-US>observer</span>，输出相关视频到<span lang=EN-US>mlg</span></span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<h3><a name="_Toc37241795">直接开启屏幕共享直播流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>通过<span lang=EN-US>api</span>接口发送开启直播命令，其中成员列表参数，带有屏幕共享类型</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>生成新的直播会话记录，分别向<span lang=EN-US>mlg</span>，<span
lang=EN-US>mcu, mps</span>获取相关资源 </span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>收到命令，检查成员列表，哪些是屏幕视频，哪些是成员视频，分别通知到<span lang=EN-US>mas</span>，将相关媒体发送到<span
lang=EN-US>mcu</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>5.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>根据成员列表，创建<span lang=EN-US>mcu</span>的<span
lang=EN-US>observer</span>，输出相关视频到<span lang=EN-US>mlg</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>通知<span lang=EN-US>mps</span>将混音流发送<span
lang=EN-US>mlg</span></span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>5.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mlg</span><span
style='font-size:14.0pt'>收到<span lang=EN-US>mps</span>的音频与<span lang=EN-US>mcu</span>的视频后，封装成<span
lang=EN-US>rtmp</span>流，发送到直播系统</span></p>

<h3><a name="_Toc37241796">一个会议同时有两个或以上直播或录像流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1．<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>开始第一个直播，指定输出成员列表，生成一个直播会话记录，开始直播</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2．<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>开始第二直播，指定输出成员列表，生成一个新直播会话记录，开始第二个直播</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<h3><a name="_Toc37241797">多人自动模式添加，删除成员流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>开始直播，设置自动模式</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-US style='font-size:14.0pt'>Mcs</span><span
style='font-size:14.0pt'>将当前会议所有人，设置输出列表</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>有新人加入会议， 自动将该入，加入直播输出列表中</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>4.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>有人退出会议，自动将该人，播出列表中删除，</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:0cm'><span
lang=EN-US>&nbsp;</span></p>

<h3><a name="_Toc37241798">多人自动模式手动模式切换流程</a></h3>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>1.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>自动模式输出所有人视频</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>2.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>切换手动模式后，需要指定输出成员</span></p>

<p class=MsoListParagraph style='margin-left:18.0pt;text-indent:-18.0pt'><span
lang=EN-US style='font-size:14.0pt'>3.<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:14.0pt'>手动模式，如果有人退会议，且在输出列表中，需要删除，如是不在列表中，不需要处理</span></p>

<h3><a name="_Toc37241799">第三方会议接入流程</a></h3>

<p class=MsoNormal>待补充</p>

<h2><a name="_Toc37241800">数据结构设计</a></h2>

<h3><a name="_Toc37241801">会议录像与直播实体关联图</a></h3>

<p class=MsoNormal><span lang=EN-US><img width=634 height=447
src="conf_live_record.files/image008.png"></span></p>

<p class=MsoNormal><span style='font-size:14.0pt'>会议<span lang=EN-US>—</span>会议成员<span
lang=EN-US>(1</span>对多<span lang=EN-US>)</span></span></p>

<p class=MsoNormal><span style='font-size:14.0pt'>会议<span lang=EN-US>—</span>录像会话<span
lang=EN-US>(1</span>对多<span lang=EN-US>)</span></span></p>

<p class=MsoNormal><span style='font-size:14.0pt'>会议<span lang=EN-US>—</span>直播会话<span
lang=EN-US>(1</span>对多<span lang=EN-US>)</span></span></p>

<p class=MsoNormal><span style='font-size:14.0pt'>录像会话<span lang=EN-US>—</span>会议成员<span
lang=EN-US>(</span>多对多<span lang=EN-US>)</span></span></p>

<p class=MsoNormal><span style='font-size:14.0pt'>直播会话<span lang=EN-US>—</span>会议成员<span
lang=EN-US>(</span>多对多<span lang=EN-US>)</span></span></p>

<h3><a name="_Toc37241802">会议实体信息</a></h3>

<p class=MsoNormal style='text-indent:21.0pt'>会议<span lang=EN-US>ID</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>会议号</p>

<p class=MsoNormal style='text-indent:21.0pt'>成员列表</p>

<p class=MsoNormal style='text-indent:21.0pt'>录像会话列表</p>

<p class=MsoNormal style='text-indent:21.0pt'>直播会话列表</p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp; </span></p>

<h3><a name="_Toc37241803">会议成员信息</a></h3>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; </span>成员<span
lang=EN-US>ID </span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; </span>会议<span
lang=EN-US>ID</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; uuid</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; </span>音频参数</p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; </span>视频参数</p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; </span>共享屏幕参数</p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; </span>录像会话列表</p>

<p class=MsoNormal><span lang=EN-US>&nbsp;&nbsp;&nbsp;&nbsp; </span>直播会话列表</p>

<h3><a name="_Toc37241804">录像会话</a></h3>

<p class=MsoNormal style='text-indent:21.0pt'>录像会话<span lang=EN-US>id</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>会议<span lang=EN-US>ID</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>输出<span lang=EN-US>ssrc</span></p>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>Mcu</span>地址与端口</p>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>Mps</span>地址与端口</p>

<p class=MsoNormal style='text-indent:21.0pt'>录像成员列表</p>

<p class=MsoNormal style='text-indent:21.0pt'>输出类型<span lang=EN-US>:</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>输出名称</p>

<p class=MsoNormal style='text-indent:21.0pt'>输出路径</p>

<p class=MsoNormal style='text-indent:21.0pt'>画面布局参数</p>

<p class=MsoNormal style='text-indent:21.0pt'>媒体输出参数</p>

<p class=MsoNormal style='text-indent:21.0pt'>会话状态</p>

<p class=MsoNormal style='text-indent:21.0pt'>开始时间</p>

<p class=MsoNormal style='text-indent:21.0pt'>结束时间</p>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>&nbsp;</span></p>

<h3><a name="_Toc37241805">录像文件列表</a></h3>

<p class=MsoNormal style='text-indent:21.0pt'>录像会话<span lang=EN-US>ID</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>会议<span lang=EN-US>ID</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>录像时长</p>

<p class=MsoNormal style='text-indent:21.0pt'>录像大小</p>

<p class=MsoNormal style='text-indent:21.0pt'>录像文件全名</p>

<p class=MsoNormal style='text-indent:21.0pt'>下载地址</p>

<p class=MsoNormal style='text-indent:21.0pt'>录像状态</p>

<p class=MsoNormal style='text-indent:21.0pt'>开始时间</p>

<p class=MsoNormal style='text-indent:21.0pt'>结束时间</p>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>&nbsp;</span></p>

<h3><a name="_Toc37241806">直播会话</a></h3>

<p class=MsoNormal style='text-indent:21.0pt'>直播会话<span lang=EN-US>id</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>会议<span lang=EN-US>ID</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>输出<span lang=EN-US>ssrc</span></p>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>Mcu</span>地址与端口</p>

<p class=MsoNormal style='text-indent:21.0pt'><span lang=EN-US>Mps</span>地址与端口</p>

<p class=MsoNormal style='text-indent:21.0pt'>直播成员列表</p>

<p class=MsoNormal style='text-indent:21.0pt'>直播频道<span lang=EN-US>ID</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>直播<span lang=EN-US>UID</span></p>

<p class=MsoNormal style='text-indent:21.0pt'>直播推流地址</p>

<p class=MsoNormal style='text-indent:21.0pt'>直播播放地址</p>

<p class=MsoNormal style='text-indent:21.0pt'>画面布局参数</p>

<p class=MsoNormal style='text-indent:21.0pt'>媒体输出参数</p>

<p class=MsoNormal style='text-indent:21.0pt'>会话状态</p>

<p class=MsoNormal style='text-indent:21.0pt'>开始时间</p>

<p class=MsoNormal style='text-indent:21.0pt'>结束时间</p>

<h1><a name="_Toc37241807">系统测试</a></h1>

<h2><a name="_Toc37241808">测试用例</a></h2>

<p class=MsoNormal><b><span style='font-size:14.0pt'>用例详细描述请参考<span lang=EN-US>&lt;&lt;</span>会议直播与录像用例<span
lang=EN-US>.xlsx&gt;&gt;</span></span></b></p>

<table class=MsoNormalTable border=0 cellspacing=0 cellpadding=0 width=585
 style='width:439.0pt;border-collapse:collapse'>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#D9D9D9;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>用例编号</span></b></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#D9D9D9;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><b><span
  style='font-size:11.0pt;color:black'>测试用例描述</span></b></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>1</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>创建会议同时加入会议<span lang=EN-US>,</span>并开启直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>2</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议已创建且已直播，有人加入会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>3</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议已创建且已直播，已有多人加入会议，再加入会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>4</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>多人加入会议直播，<span lang=EN-US>1</span>，<span lang=EN-US>2</span>，<span
  lang=EN-US>3</span>，<span lang=EN-US>7</span>，<span lang=EN-US>20</span>，<span
  lang=EN-US>36</span>，<span lang=EN-US>37</span>人加入会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>5</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议同时多人加入会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>6</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一人加入会议后，又退出会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>7</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>多人同时退出会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>8</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议创建人员，解散会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>9</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议中最后一个人退出</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>10</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>多种类型终端加入会议<span lang=EN-US>,pc, </span>手机，硬件等</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>11</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>停止会议直播后，重新设置新的直播参数后直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>12</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>启动不存在会议直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>13</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>停止不存在会议直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>14</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>加入不存在会议的成员</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>15</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>退出不存在会义中的成员</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>16</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>一次多入加入会议时，期中有非法成员</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>17</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播时，<span lang=EN-US>mlg</span>服务异常</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>18</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播时，<span lang=EN-US>mcu</span>服务异常</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>19</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播时，<span lang=EN-US>mas</span>服务异常</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>20</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播时，<span lang=EN-US>mps</span>服务异常</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>21</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播时，<span lang=EN-US>mcs</span>服务异常</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>22</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议中，每个成员<span lang=EN-US>1</span>个直播频道</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>23</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议中，一个人输出<span lang=EN-US>2</span>个直播频道</span></p>
  </td>
 </tr>
 <tr style='height:28.5pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>24</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议中，所有人输出一直播频道，其中有人会输出另外的直播频道</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>25</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同会议，同一人输出，<span lang=EN-US>5</span>，<span lang=EN-US>10</span>，<span
  lang=EN-US>20</span>个直播频道</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>26</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同会议，输出多个直播频道，<span lang=EN-US>5</span>，<span lang=EN-US>10</span>，<span
  lang=EN-US>20</span>，<span lang=EN-US>30</span>，<span lang=EN-US>40</span>直播频道</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>27</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>在会议中，有人开启共享屏幕，输出直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>28</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>需要看人员的成员视频与共享屏幕，直播</span></p>
  </td>
 </tr>
 <tr style='height:28.5pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>29</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议中，有人已开启共享屏幕，另外有也尝试开启共享屏幕</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>30</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>共享屏幕输出到一个直播频道，成员视频输出到另一人直播频道</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>31</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播没有开启，直接共享屏幕直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>32</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>来回切换共享与成员视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>33</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播开始指定分辨率 如<span lang=EN-US>1280x720x15</span></span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>34</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>修改新的参数输出</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>35</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>横屏输出</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>36</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>竖屏输出</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>37</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播中，不断增减成员，</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>38</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>一会议输出画面输出最大成员数</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>39</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>参数输出一些不支持的参数如<span lang=EN-US>1123x553</span></span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>40</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议一开始，就开始直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>41</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始后，多人进入会议后，开始直播</span></p>
  </td>
 </tr>
 <tr style='height:28.5pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>42</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>创建会议后，没有任何人加入会议的视频时开始直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>43</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始直播，不断有入加入会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>44</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播中， 不断有人退出会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>45</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播中，有多人正在开会，直接解散会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>46</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始后，指定某人或某几人直播输出，其他不输出</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>47</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播输出时，没有在直播中的人退出会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>48</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同会议，有多个直播输出，直播中的人员退出会议</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>49</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>所有人退会议或解散时，停止所有该会议所有直播输出</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>50</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>指定会议成员直播时，成员<span lang=EN-US>id</span>不在该会议中</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>51</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始后，直播输出只有声音</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>52</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始后，直播输出只有视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>53</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始后，有两个直播频道，一个只输出声音，一个只输出视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>54</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议，开启直播与录像， 直播与录像画面是一样的</span></p>
  </td>
 </tr>
 <tr style='height:28.5pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>55</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议，直播输出成员视频，录像输出共享屏幕</span></p>
  </td>
 </tr>
 <tr style='height:28.5pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>56</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议，直播输出共享屏幕，录像输出成员视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>57</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议，直播输出所有成员视频， 录像输出某个成员视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>58</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议，有直播输出与录像输出，停止直播输出</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>59</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同一会议，有直播输出与录像输出，停止录像</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>60</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同时直播与录像输出某人视频， 之后该人退出会议， 还有其他人</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>61</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>同时直播与录像输出某人视频， 之后该人退出会议， 没有其他人</span></p>
  </td>
 </tr>
 <tr style='height:16.5pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:16.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:16.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>62</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议没有结束， 中途录像启停多次</span></p>
  </td>
 </tr>
 <tr style='height:17.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:17.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>63</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:17.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始后，一直没有停止过，长达<span lang=EN-US>1</span>，<span
  lang=EN-US>2</span>，<span lang=EN-US>3</span>，<span lang=EN-US>4</span>，<span
  lang=EN-US>5</span>，<span lang=EN-US>6</span>个小时，或更长的时间</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>64</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始，录像开始后，马上停止录像，时间相隔比较短</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>65</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像开始时，指定输出<span lang=EN-US>flv</span>文件</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>66</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像开始时，指定输出<span lang=EN-US>mp4</span>文件</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>67</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像开始时，指定同时输出<span lang=EN-US>flv,mp4</span>文件</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>68</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像开始时，视频指定输出<span lang=EN-US>h264</span>祼流文件</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>69</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像开始时，音频指定输出<span lang=EN-US>aac</span>文件</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>70</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>录像<span lang=EN-US>mp4,flv</span>的同时，输出<span lang=EN-US>h264,aac</span>文件</span></p>
  </td>
 </tr>
 <tr style='height:28.5pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>71</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:28.5pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>有可能有多个录像，需要获取会议的所有录像文件，需要知道录像时间，大小等等</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>72</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议开始后， 将输出可以生成<span lang=EN-US>jpg</span>截图</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>73</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span lang=EN-US
  style='font-size:11.0pt;color:black'>jpg</span><span style='font-size:11.0pt;
  color:black'>截图一直生成，直到会议结束</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>74</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议输出截图，不断输出当前画面截图</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;background:#BDD7EE;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>　</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>75</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>直播后，会议本地预览视频与直播显示的视频延迟</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>76</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span lang=EN-US
  style='font-size:11.0pt;color:black'>mcu</span><span style='font-size:11.0pt;
  color:black'>与<span lang=EN-US>mlg </span>在同一机器，会议直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>77</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span lang=EN-US
  style='font-size:11.0pt;color:black'>mcu</span><span style='font-size:11.0pt;
  color:black'>与<span lang=EN-US>mlg </span>不在同一机器，但在同一局域网内，会议直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>78</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span lang=EN-US
  style='font-size:11.0pt;color:black'>mcu</span><span style='font-size:11.0pt;
  color:black'>与<span lang=EN-US>mlg</span>使用外网会议直播</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>79</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议视频的有卡顿，检查直播与录像的画面</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>80</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议视频非常流畅，无卡顿，检查会议直播与录像后的画面</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>81</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>会议直播后，在终端关闭视频，直播画面应该消失</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>82</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>直播后，终端关闭视频后，又开启视频</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>83</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>直播后，终端关闭声音</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>84</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>直播后，终端关闭声音，以开启声音</span></p>
  </td>
 </tr>
 <tr style='height:14.25pt'>
  <td width=67 nowrap valign=bottom style='width:50.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=right style='text-align:right'><span lang=EN-US
  style='font-size:11.0pt;color:black'>85</span></p>
  </td>
  <td width=519 valign=bottom style='width:389.0pt;padding:0cm 5.4pt 0cm 5.4pt;
  height:14.25pt'>
  <p class=MsoNormal align=left style='text-align:left'><span style='font-size:
  11.0pt;color:black'>直播后，终端同时关闭声音与视频</span></p>
  </td>
 </tr>
</table>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

</div>

</body>

</html>
