**Introduction**

The vanilla Liferay DXP 7.4 (2023.q4.4) throws a HTTP 404 error when a user attempts to preview an Expired Web Content article via a Display Page Template.

This is a result of the logic within the _isShow(JournalArticle article) method of JournalArticleLayoutDisplayPageObjectProvider.java class. This OSGi based customization removes the 'isExpired' check from the _isShow(JournalArticle article) method with a custom JournalArticleLayoutDisplayPageObjectProvider.java class with a higher service ranking.

With the customization deployed the Expired Web Content articles should now be previewable.

**Notes**

This module has been tested in a DXP 7.4 (2023.q4.4) using JDK8 for compile and runtime. It should also work with JDK 11.

This should be used in an environment without this hotfix: liferay-dxp-2023.q4.4-hotfix-300.zip

Please fully test all scenarios related to Web Content (in a non production environment) to ensure this customization hasn't introduced any issues.
