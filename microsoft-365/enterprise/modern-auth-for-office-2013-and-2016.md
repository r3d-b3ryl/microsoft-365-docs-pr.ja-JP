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
description: 2013 Microsoft 365 2016 クライアント アプリの最新の認証機能の動作Officeについて学習します。
ms.openlocfilehash: 60b1729d9830fd12141d162c4fe721267e52d437
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220794"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>2013、Office 2016、および 2019 Office 2019 クライアント アプリOfficeのしくみ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事では、Office、Office 2016、および Office 2019 クライアント アプリが Exchange Online、SharePoint Online、および Skype for Business Online の Microsoft 365 テナントの認証構成に基づいて最新の認証機能を使用する方法について説明します。

> [!NOTE]
> 従来のクライアント アプリ (Office 2010 や Office for Mac 2011 など) は、最新の認証をサポートしていないので、基本認証でのみ使用できます。

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>サービスの最新の認証Microsoft 365利用可能

最新のMicrosoft 365の既定の状態は次の場合です。

- 既定 **では、Exchange Online** オンになっています。 有効[または無効にする方法については、「Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662)で最新の認証を有効または無効にする」を参照してください。

- 既定 **では、[** オンライン] SharePointオンになっています。

- 既定 **では、[** オンラインSkype for Businessオンになっています。 「[モダン認証Skype for Businessオンラインを有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)」を参照してください。

> [!NOTE]
> 2017 年 8 月 1 日より **前** に作成されたテナントでは、Exchange Online と Skype for Business Online は既定で **オフ** になっています。

## <a name="sign-in-behavior-of-office-client-apps"></a>クライアント アプリのサインインOffice動作

Office 2013 クライアント アプリは、既定で従来の認証をサポートしています。 レガシとは、Microsoft Online サインイン アシスタントまたは基本認証のいずれかをサポートしているという意味です。 これらのクライアントが最新の認証機能を使用するには、Windowsレジストリ キーが設定されている必要があります。 手順については、「Enable [Modern Authentication for Office 2013 on Windows」を参照してください](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)。

Microsoft Office 2013 がインストールされている Windows を実行しているデバイス (たとえばノート PC やタブレット) で先進認証を有効にするには、次のレジストリ キーを設定する必要があります。先進認証を有効にするデバイスごとに、次のキーを設定する必要があります。

|**レジストリ キー**|**型**|**値** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |

詳細については[、「モダン認証 (ADAL)](./hybrid-modern-auth-overview.md)を使用する方法 」を参照Skype for Business Skype for Businessを参照してください。

Office 2016 および Office 2019 のクライアントは既定で最新の認証をサポートしています。クライアントがこれらの新しいフローを使用する場合は、アクションは必要とされません。 ただし、従来の認証を使用するには、明示的なアクションが必要です。

次のリンクをクリックして、Office 2013、Office 2016、Office 2019 クライアント認証が最新の認証を有効にするかどうかに応じて Microsoft 365 サービスと動作する方法を確認します。

- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)

- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)

- [Skype for Business Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)

<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

次の表は、Office 2013、Office 2016、Office 2019 クライアント アプリが最新の認証の場合と接続しない場合の Exchange Online の認証動作を示しています。

|Office アプリのバージョン****|レジストリ キーが存在する?****|最新の認証 on?****|テナントに対して最新の認証を有効にした認証動作 (default)****|テナントの最新の認証を無効にした認証動作****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |違います <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |はい  <br/> |2013 年、2016 年Outlook 2019 年に最新の認証を強制的に実行します。 <br/> [詳細情報](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|クライアント内で最新の認証Outlookします。<br/> |
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL=0  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2016  <br/> |違います <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |はい  <br/> |2013、2016、または 2019 で最新の認証を強制的に実行します。 <br/> [詳細情報](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|クライアント内で最新の認証Outlookします。<br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL=0  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは最新の認証を拒否します。  <br/> |

<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

次の表は、Office 2013、Office 2016、および Office 2019 クライアント アプリが最新の認証の場合またはない場合に SharePoint Online に接続する場合の認証動作について説明します。

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

次の表では、Office 2013、Office 2016、および Office 2019 クライアント アプリが最新の認証の場合と接続しない場合の Skype for Business Online への接続時の認証動作について説明します。

|Office アプリのバージョン****|レジストリ キーが存在する?****|最新の認証 on?****|テナントの最新の認証を有効にした認証動作****|テナントの最新の認証を無効にした認証動作 (default)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |最新の認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 オンライン テナントが有効になっていない場合Skype for Businessサーバーは最新の認証を拒否します。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |

## <a name="see-also"></a>関連項目

[Windows デバイスの Office 2013 の先進認証を有効にする](../admin/security-and-compliance/enable-modern-authentication.md)

[Microsoft 365 の多要素認証](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[多要素認証Microsoft 365サインインする](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)