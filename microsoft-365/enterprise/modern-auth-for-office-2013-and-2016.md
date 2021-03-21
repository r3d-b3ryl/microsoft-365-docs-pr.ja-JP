---
title: Office 2013 クライアント アプリと Office 2016 クライアント アプリでの先進認証のしくみ
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Microsoft 365 の最新の認証機能が、2016 クライアント アプリと 2016 Office 2013しく動作する方法について説明します。
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921668"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>最新の認証が 2016 年Office 2013 2016 年Office 2019 年クライアント アプリOffice動作する方法

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事では、Office 2013、Office 2016、および Office 2019 クライアント アプリが、Exchange Online、SharePoint Online、Skype for Business Online の Microsoft 365 テナントの認証構成に基づいて最新の認証機能を使用する方法について説明します。

> [!NOTE]
> 従来のクライアント アプリ (Office 2010 や Office for Mac 2011 など) は、最新の認証をサポートしていないので、基本認証でのみ使用できます。

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Microsoft 365 サービスの最新の認証の可用性

Microsoft 365 サービスの場合、最新の認証の既定の状態は次です。
  
- Exchange **Online で** 既定で有効になっています。 [「Exchange Online で最新の認証を有効または無効](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662)にする」を参照して、無効または無効にします。 
    
- 既定 **では** 、SharePoint Online で有効になっています。 
    
- 既定 **では** 、Skype for Business Online で有効になっています。 「Skype [for Business Online for Modern authentication for Enable Skype for Business Online」 ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)を参照して、有効または無効にします。

> [!NOTE]
> 2017 年 8 月 1 日より **前** に作成されたテナントでは、Exchange Online と Skype for Business Online は既定で **オフ** になっています。
    
## <a name="sign-in-behavior-of-office-client-apps"></a>クライアント アプリのサインインOffice動作

Office 2013クライアント アプリは、既定で従来の認証をサポートしています。 レガシとは、Microsoft Online サインイン アシスタントまたは基本認証のいずれかをサポートしているという意味です。 これらのクライアントが最新の認証機能を使用するには、Windows クライアントにレジストリ キーが設定されている必要があります。 手順については、「Windows デバイスで [最新の認証を有効にする」Office 2013を参照してください](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)。

Microsoft Office 2013 がインストールされている Windows を実行しているデバイス (たとえばノート PC やタブレット) で先進認証を有効にするには、次のレジストリ キーを設定する必要があります。先進認証を有効にするデバイスごとに、次のキーを設定する必要があります。
  
|**レジストリ キー**|**型**|**値** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Skype for Business [でモダン認証 (ADAL)](./hybrid-modern-auth-overview.md) を使用する方法を参照して、Skype for Business での動作について説明します。 
  
Office 2016 および Office 2019 のクライアントは既定で最新の認証をサポートします。クライアントがこれらの新しいフローを使用する操作は必要とされません。 ただし、従来の認証を使用するには、明示的なアクションが必要です。
  
次のリンクをクリックして、Office 2013、Office 2016、Office 2019 クライアント認証が Microsoft 365 サービスとどのように動作するかは、最新の認証が有効になっているかどうかに応じて確認できます。
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype for Business Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

次の表は、Office 2013、Office 2016、および Office 2019 クライアント アプリが最新の認証の場合と接続しない場合の認証動作について説明します。
  
|Office アプリのバージョン****|レジストリ キーが存在する?****|最新の認証 on?****|テナントに対して最新の認証を有効にした認証動作 (default)****|テナントの最新の認証を無効にした認証動作****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |違います <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |はい  <br/> |Outlook 2013、2016、または 2019 で最新の認証を強制的に実行します。 <br/> [詳細情報](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Outlook クライアント内で最新の認証を強制的に実行します。<br/> |
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL=0  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2016  <br/> |違います <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |はい  <br/> |2013、2016、または 2019 で最新の認証を強制的に実行します。 <br/> [詳細情報](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Outlook クライアント内で最新の認証を強制的に実行します。<br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL=0  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

次の表では、Office 2013、Office 2016、および Office 2019 クライアント アプリが最新の認証の場合と接続しない場合の認証動作について説明します。
  
|Office アプリのバージョン****|レジストリ キーが存在する?****|最新の認証 on?****|テナントに対して最新の認証を有効にした認証動作 (default)****|テナントの最新の認証を無効にした認証動作****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証のみ。  <br/> |接続に失敗しました。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証のみ。  <br/> |接続に失敗しました。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証のみ。  <br/> |接続に失敗しました。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証のみ。  <br/> |接続に失敗しました。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証のみ。  <br/> |接続に失敗しました。  <br/> |
   
### <a name="skype-for-business-online"></a>Skype for Business Online
<a name="BK_SFBO"> </a>

次の表は、Office 2013、Office 2016、および Office 2019 クライアント アプリが Skype for Business Online に接続する場合の、最新の認証の場合と接続しない場合の認証動作について説明します。
  
|Office アプリのバージョン****|レジストリ キーが存在する?****|最新の認証 on?****|テナントの最新の認証を有効にした認証動作****|テナントの最新の認証を無効にした認証動作 (default)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
   
## <a name="see-also"></a>関連項目

[Windows デバイスの Office 2013 の先進認証を有効にする](../admin/security-and-compliance/enable-modern-authentication.md)

[Microsoft 365 の多要素認証](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[多要素認証を使用して Microsoft 365 にサインインする](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)