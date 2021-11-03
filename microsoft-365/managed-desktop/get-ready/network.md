---
title: Microsoft マネージド デスクトップのネットワーク構成
description: プロキシと必要なエンドポイントを設定する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 43207493a33c002d8137ecf3604393b06a15c17e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662441"
---
#  <a name="network-configuration-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのネットワーク構成

<!--Proxy config -->


## <a name="proxy-configuration"></a>プロキシ構成

Microsoft Managed Desktop はクラウド管理サービスです。 Microsoft Managed Desktop サービスが到達できる必要がある一連のエンドポイントがあります。 このセクションでは、Microsoft Managed Desktop サービスのさまざまな側面で許可する必要があるエンドポイントの一覧を示します。 

お客様は、ファイアウォールまたはプロキシを介してMicrosoft 365ネットワーク要求を直接送信し、認証をバイパスし、追加のパケット レベルの検査または処理を行って、ネットワークを最適化できます。 これにより、待機時間と境界の容量要件が削減されます。 

また、Microsoft Managed Desktop クラウドベースのサービスに対するパフォーマンスを最適化するには、これらのエンドポイントでは、顧客のクライアント ブラウザーとエッジ ネットワーク内のデバイスによる特別な処理が必要です。 これらのデバイスには、ファイアウォール、SSL Break and Inspect、パケット検査デバイス、およびデータ損失防止システムが含まれます。

### <a name="proxy-requirement"></a>プロキシ要件

プロキシまたはファイアウォールは TLS 1.2 をサポートしている必要があります。 それ以外の場合は、プロトコル検出を無効にする必要があります。

### <a name="allowed-endpoints-that-are-necessary-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop に必要な許可エンドポイント

Microsoft Managed Desktop は、Azure Portal を使用して Web コンソールをホストします。 Microsoft Managed Desktop デバイスが Microsoft Services と通信するには、プロキシとファイアウォールの許可リストに次の URL が必要です。  

Microsoft Managed Desktop URL は、お客様の API でサービスが実行される場合に使用されます。 この URL は、企業ネットワーク上で常にアクセス可能である必要があります。

Microsoft サービス  | 許可リストに必要な URL 
--- | ---
Microsoft マネージド デスクトップ | prod-mwaas-services-customerapi.azurewebsites.net <br>mmd-support-prod-nam.trafficmanager.net <br>mmdls.microsoft.com
問い合わせ | \*.support.services.microsoft.com  <br>inprod.support.services.microsoft.com  <br>supportchannels.services.microsoft.com  <br>graph.windows.net  <br>login.windows.net  <br>prod-mwaas-services-customerapi.azurewebsites.net  <br>concierge.live.com
クイック アシスト | remoteassistance.support.services.microsoft.com <br>relay.support.services.microsoft.com <br>channelwebsdks.azureedge.net  <br>web.vortex.data.microsoft.com  <br>gateway.channelservices.microsoft.com <br>\*.lync.com
Microsoft サポート/回復アシスタント | \*.apibasic.diagnostics.office.com  <br>\*.api.diagnostics.office.com
 
### <a name="allowed-endpoints-used-by-other-microsoft-products"></a>他の Microsoft 製品で使用できるエンドポイント

Microsoft Managed Desktop デバイスがそれらの Microsoft サービスと通信するために、許可されているリストに含む必要がある複数の Microsoft 製品の URL があります。 各製品の完全な一覧を表示するには、リンクを使用します。 

Microsoft サービス | ドキュメント
--- | ---
Windows 10 Enterprise更新プログラムWindows含む | [バージョン 1803 の Windows 10エンドポイントを管理する](/windows/privacy/manage-windows-1803-endpoints)<br><br>[ユーザーの接続エンドポイントをWindows 10 Version 1809](/windows/privacy/manage-windows-1809-endpoints)<br><br>[バージョン 1903 の Windows 10エンドポイントを管理する](/windows/privacy/manage-windows-1903-endpoints)<br><br>[バージョン 2004 Windows 10の接続エンドポイントを管理する](/windows/privacy/manage-windows-2004-endpoints)
配信最適化 | [配信の最適化を構成して、Windows 10更新プログラムを構成する](/windows/deployment/update/waas-delivery-optimization)
Microsoft 365 | [Microsoft 365URL と IP アドレスの範囲](../../enterprise/urls-and-ip-address-ranges.md)
Azure Active Directory | [ハイブリッド ID が必要なポートとプロトコルと](/azure/active-directory/hybrid/reference-connect-ports) [Active Directory と Active Directory ドメイン サービスのポート要件](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd772723(v=ws.10)) 
Microsoft Intune | [Intune ネットワーク構成の要件](/intune/network-bandwidth-use)<br>[ネットワーク エンドポイントのMicrosoft Intune](/mem/intune/fundamentals/intune-endpoints)
Microsoft Defender for Endpoint | [Microsoft Defender for Endpoint の要件](/windows/security/threat-protection/windows-defender-atp/configure-proxy-internet-windows-defender-advanced-threat-protection#enable-access-to-windows-defender-atp-service-urls-in-the-proxy-server)
Windows Autopilot | [WindowsAutopilot ネットワーク要件](/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)

Microsoft サービス  | 許可リストに必要な URL | ドキュメント ソース
--- | --- | ---
Windowsビジネス向け更新プログラム (WUfB) | update.microsoft.com<br>\*.update.microsoft.com<br>download.windowsupdate.com<br>\*.download.windowsupdate.com<br>download.microsoft.com<br>\*.download.microsoft.com<br>windowsupdate.com<br>\*.windowsupdate.com<br>ntservicepack.microsoft.com<br>wustat.windows.com<br>login.live.com <br>mp.microsoft.com<br>\*.mp.microsoft.com | [Windowsビジネス ファイアウォールとプロキシの要件の更新](https://support.microsoft.com/help/3084568/can-t-download-updates-from-windows-update-from-behind-a-firewall-or-p)
配信最適化 | \*.do.dsp.mp.microsoft.com<br>\*.dl.delivery.mp.microsoft.com <br>\*.emdl.ws.microsoft.com<br>\*.download.windowsupdate.com <br>\*.windowsupdate.com   | [Windowsプロキシ要件の更新](https://support.microsoft.com/help/3175743/proxy-requirements-for-windows-update)
ビジネス向け Microsoft Store | login.live.com <br>account.live.com <br>clientconfig.passport.net <br>wustat.windows.com <br>\*.windowsupdate.com <br>\*.wns.windows.com <br>\*.hotmail.com <br>\*.outlook.com <br>\*.microsoft.com <br>\*.msftncsi.com/ncsi.txt   | [Microsoft Store許可リスト](https://support.microsoft.com/help/2778122/using-authenticated-proxy-servers-together-with-windows-8)
Microsoft 365 | \*.office365.com<br>\*.office.com<br>\*.office.net<br>\*.live.com<br>\*.portal.cloudappsecurity.com<br>\*.portal.cloudappsecurity.com<br>\*.us.portal.cloudappsecurity.com<br>\*.eu.portal.cloudappsecurity.com<br>\*.us2.portal.cloudappsecurity.com<br><tenant>.onmicrosoft.com<br>account.office.net<br>agent.office.net<br>apc.delve.office.com<br>aus.delve.office.com<br>can.delve.office.com<br>delve.office.com<br>eur.delve.office.com<br>gbr.delve.office.com<br>home.office.com<br>ind.delve.office.com<br>jpn.delve.office.com<br>kor.delve.office.com<br>lam.delve.office.com<br>nam.delve.office.com<br>admin.microsoft.com<br>outlook.office365.com<br>suite.office.net<br>webshell.suite.office.com<br>www.office.com<br>\*.aria.microsoft.com<br>browser.pipe.aria.microsoft.com<br>mobile.pipe.aria.microsoft.com<br>portal.microsoftonline.com<br>clientlog.admin.microsoft.com<br>nexus.officeapps.live.com<br>nexusrules.officeapps.live.com<br>amp.azure.net<br>\*.o365weve.com<br>auth.gfx.ms<br>appsforoffice.microsoft.com<br>assets.onestore.ms<br>az826701.vo.msecnd.net<br>c.microsoft.com<br>c1.microsoft.com<br>client.hip.live.com<br>contentstorage.osi.office.net<br>dgps.support.microsoft.com<br>docs.microsoft.com<br>groupsapi-<br>rod.outlookgroups.ms<br>groupsapi2-prod.outlookgroups.ms<br>groupsapi3-prod.outlookgroups.ms<br>groupsapi4-prod.outlookgroups.ms<br>msdn.microsoft.com<br>platform.linkedin.com<br>products.office.com<br>prod.msocdn.com<br>r1.res.office365.com<br>r4.res.office365.com<br>res.delve.office.com<br>shellprod.msocdn.com<br>support.content.office.net<br>support.microsoft.com<br>support.office.com<br>technet.microsoft.com<br>templates.office.com<br>video.osi.office.net<br>videocontent.osi.office.net<br>videoplayercdn.osi.office.net<br>\*.manage.office.com<br>\*.protection.office.com<br>manage.office.com<br>Protection.office.com<br>diagnostics.office.com | [Microsoft 365URL と IP アドレスの範囲](../../enterprise/urls-and-ip-address-ranges.md)
Azure Active Directory | api.login.microsoftonline.com<br>api.passwordreset.microsoftonline.com<br>autologon.microsoftazuread-sso.com<br>becws.microsoftonline.com<br>clientconfig.microsoftonline-p.net <br>companymanager.microsoftonline.com <br>device.login.microsoftonline.com <br>hip.microsoftonline-p.net <br>hipservice.microsoftonline.com <br>login.microsoft.com<br>login.microsoftonline.com <br>logincert.microsoftonline.com <br>loginex.microsoftonline.com<br>login-us.microsoftonline.com <br>login.microsoftonline-p.com <br>login.windows.net <br>nexus.microsoftonline-p.com <br>passwordreset.microsoftonline.com <br>provisioningapi.microsoftonline.com<br>stamp2.login.microsoftonline.com<br>\*.msappproxy.net<br>ccs.login.microsoftonline.com<br>ccs-sdf.login.microsoftonline.com<br>accounts.accesscontrol.windows.net<br>secure.aadcdn.microsoftonline-p.com<br>\*.phonefactor.net<br>account.activedirectory.windowsazure.com<br>secure.aadcdn.microsoftonline-p.com<br>graph.microsoft.com | [ハイブリッド ID が必要なポートとプロトコルと](/azure/active-directory/connect/active-directory-aadconnect-ports) [Active Directory と Active Directory ドメイン サービスのポート要件](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd772723(v=ws.10)) 
Microsoft Intune | login.microsoftonline.com<br>portal.manage.microsoft.com<br>m.manage.microsoft.com<br>sts.manage.microsoft.com<br>Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com<br>fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fef.msua01.manage.microsoft.com<br>fef.msua02.manage.microsoft.com<br>fef.msua04.manage.microsoft.com<br>fef.msua05.manage.microsoft.com<br>fef.msua06.manage.microsoft.com<br>fef.msua07.manage.microsoft.com<br>fef.msub01.manage.microsoft.com<br>fef.msub02.manage.microsoft.com<br>fef.msub03.manage.microsoft.com<br>fef.msub05.manage.microsoft.com<br>fef.msuc01.manage.microsoft.com<br>fef.msuc02.manage.microsoft.com<br>fef.msuc03.manage.microsoft.com<br>fef.msuc05.manage.microsoft.com |  [Intune ネットワーク構成の要件](/intune/network-bandwidth-use)
OneDrive for Business | onedrive.com <br> <br>\*.onedrive.com <br>onedrive.live.com <br>login.live.com <br>spoprod-a.akamaihd.net <br>\*.mesh.com <br>p.sfx.ms <br>\*.microsoft.com <br>fabric.io <br>\*.crashlytics.com <br>vortex.data.microsoft.com <br>https://posarprodcssservice.accesscontrol.windows.net <br>redemptionservices.accesscontrol.windows.net  <br>token.cp.microsoft.com/ <br>tokensit.cp.microsoft-tst.com/ <br>\*.office.com <br>\*.officeapps.live.com <br>\*.aria.microsoft.com <br>\*.mobileengagement.windows.net <br>\*.branch.io <br>\*.adjust.com <br>\*.servicebus.windows.net <br>vas.samsungapps.com <br>odc.officeapps.live.com <br>login.windows.net <br>login.microsoftonline.com <br>\*.files.1drv.com <br>\*.onedrive.live.com <br>\*.\*.onedrive.live.com <br>storage.live.com <br>\*.storage.live.com <br>\*.\*.storage.live.com <br>\*.groups.office.live.com <br>\*.groups.photos.live.com <br>\*.groups.skydrive.live.com <br>favorites.live.com <br>oauth.live.com <br>photos.live.com <br>skydrive.live.com <br>api.live.net <br>apis.live.net <br>docs.live.net <br>\*.docs.live.net <br>policies.live.net <br>\*.policies.live.net <br>settings.live.net <br>\*.settings.live.net <br>skyapi.live.net <br>snapi.live.net <br>\*.livefilestore.com <br>\*.\*.livefilestore.com <br>storage.msn.com <br>\*.storage.msn.com <br>\*.*.storage.msn.com | [ユーザーに必要な URL とポートOneDrive](/onedrive/required-urls-and-ports)
Microsoft Defender Advanced Threat Protection (ATP) | \ *.oms.opinsights.azure.com <br>\*.blob.core.windows.net <br>\*.azure-automation.net <br>\*.ods.opinsights.azure.com <br>winatp-gw-cus.microsoft.com <br>winatp-gw-eus.microsoft.com <br>winatp-gw-neu.microsoft.com <br>winatp-gw-weu.microsoft.com <br>winatp-gw-uks.microsoft.com <br>winatp-gw-ukw.microsoft.com <br>winatp-gw-aus.microsoft.com <br>winatp-gw-aue.microsoft.com | [Windows DefenderATP エンドポイント](/windows/security/threat-protection/windows-defender-atp/configure-server-endpoints-windows-defender-advanced-threat-protection)
問い合わせ | \*.support.services.microsoft.com  <br>inprod.support.services.microsoft.com  <br>supportchannels.services.microsoft.com  <br>graph.windows.net  <br>login.windows.net  <br>prod-mwaas-services-customerapi.azurewebsites.net  <br>concierge.live.com <br>rave.office.net | 
クイック アシスト | remoteassistance.support.services.microsoft.com <br>relay.support.services.microsoft.com <br>channelwebsdks.azureedge.net  <br>web.vortex.data.microsoft.com  <br>gateway.channelservices.microsoft.com <br>\*.lync.com | 
SharePoint Online  | \*.sharepoint.com <br>\ *.svc.ms  <br>\<tenant\>.sharepoint.com  <br>\<tenant\>-my.sharepoint.com  <br>\<tenant\>-files.sharepoint.com  <br>\<tenant\>-myfiles.sharepoint.com <br>\*.sharepointonline.com  <br>cdn.sharepointonline.com  <br>static.sharepointonline.com  <br>spoprod-a.akamaihd.net  <br>publiccdn.sharepointonline.com  <br>privatecdn.sharepointonline.com | [Office 365 URL および IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)
OneDrive for Business | admin.onedrive.com  <br>officeclient.microsoft.com <br>odc.officeapps.live.com  <br>skydrive.wns.windows.com <br>g.live.com <br>oneclient.sfx.ms <br>\*.log.optimizely.com  <br>click.email.microsoftonline.com  <br>ssw.live.com  <br>storage.live.com |  [Office 365 URL および IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)
Microsoft Teams | \*.teams.skype.com  <br>\*.teams.microsoft.com  <br>teams.microsoft.com <br>\*.asm.skype.com <br>\ *.cc.skype.com  <br>\*.conv.skype.com  <br>\*.dc.trouter.io  <br>\*.msg.skype.com  <br>prod.registrar.skype.com  <br>prod.tpc.skype.com <br>\*.broker.skype.com <br>\*.config.skype.com  <br>\*.pipe.skype.com  <br>\*.pipe.aria.microsoft.com  <br>config.edge.skype.com  <br>pipe.skype.com  <br>s-0001.s-msedge.net  <br>s-0004.s-msedge.net  <br>scsinstrument-ss-us.trafficmanager.net  <br>scsquery-ss- <br>us.trafficmanager.net  <br>scsquery-ss-eu.trafficmanager.net  <br>scsquery-ss-asia.trafficmanager.net <br>\*.msedge.net <br>compass-ssl.microsoft.com  <br>feedback.skype.com <br>\*.secure.skypeassets.com  <br>mlccdnprod.azureedge.net  <br>videoplayercdn.osi.office.net <br>\*.mstea.ms | [Office 365 URL および IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)
Power BI | maxcdn.bootstrapcdn.com <br>ajax.aspnetcdn.com <br>netdna.bootstrapcdn.com <br>cdn.optimizely.com <br>google-analytics.com <br>\*.mktoresp.com <br>\*.aadcdn.microsoftonline-p.com <br>\*.msecnd.com <br>\*.localytics.com <br>ajax.aspnetcdn.com <br>\*.localytics.com <br>\*.virtualearth.net <br>platform.bing.com <br>powerbi.microsoft.com <br>c.microsoft.com <br>app.powerbi.com <br>\*.powerbi.com <br>dc.services.visualstudio.com <br>support.powerbi.com <br>powerbi.uservoice.com <br>go.microsoft.com <br>c1.microsoft.com <br>\*.azureedge.net |[Power BI &エクスプレス ルート](/power-bi/service-admin-power-bi-expressroute) 
OneNote | apis.live.net <br>www.onedrive.com <br>login.microsoft.com  <br>www.onenote.com <br>\*.onenote.com <br>\*.msecnd.net <br>\*.microsoft.com <br>\*.office.net <br>cdn.onenote.net <br>site-cdn.onenote.net <br>cdn.optimizely.com <br>Ajax.aspnetcdn.com <br>officeapps.live.com <br>\\*.onenote.com <br>\*cdn.onenote.net <br>contentstorage.osi.office.net <br>\*onenote.officeapps.live.com <br>\*.microsoft.com | [Office 365 URL および IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. ネットワーク構成を確認します (この記事)。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
