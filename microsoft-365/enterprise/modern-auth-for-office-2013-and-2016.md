---
title: Office 2013 クライアント アプリと Office 2016 クライアント アプリでの先進認証のしくみ
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Office 2013 および 2016 クライアント アプリでは、Microsoft 365先進認証機能の動作が異なる方法について説明します。
ms.openlocfilehash: 9c4cdc384ceded4ce3bb78ae4e67e0f4c5a503de
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093374"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Office 2013、Office 2016、Office 2019 クライアント アプリの先進認証のしくみ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

2013、Office 2016、Office 2019 のクライアント アプリOffice、Exchange Online、SharePoint Online、およびMicrosoft 365 テナントの認証構成に基づいて先進認証機能を使用する方法については、この記事を参照してください。オンラインSkype for Business。

> [!NOTE]
> Office 2010 や Office for Mac 2011 などのレガシ クライアント アプリは、最新の認証をサポートしていないため、基本認証でのみ使用できます。

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Microsoft 365 サービスの先進認証の可用性

Microsoft 365 サービスの場合、先進認証の既定の状態は次のとおりです。

- 既定 **では**、Exchange Onlineに対してオンになっています。 [最新の認証を有効または無効にする方法については、「Exchange Onlineで最新の認証を有効または無効](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662)にする」を参照してください。

- 既定 **では、SharePoint Online で有効** になっています。

- 既定 **では、** Skype for Business Online でオンになっています。 [最新の認証に対Skype for Businessオンラインを有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)方法については、「有効にする」を参照して、この認証をオフまたはオンにします。

> [!NOTE]
> 2017 年 8 月 1 日より **前** に作成されたテナントでは、Exchange Online と Skype for Business Online は既定で **オフ** になっています。

## <a name="sign-in-behavior-of-office-client-apps"></a>Office クライアント アプリのサインイン動作

Office 2013 クライアント アプリでは、既定でレガシ認証がサポートされます。 レガシとは、Microsoft Online サインイン アシスタントまたは基本認証をサポートしていることを意味します。 これらのクライアントが最新の認証機能を使用するには、Windows クライアントにレジストリ キーが設定されている必要があります。 手順については、「[Windows デバイスでOffice 2013 の先進認証を有効にする](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)」を参照してください。

Microsoft Office 2013 がインストールされている Windows を実行しているデバイス (たとえばノート PC やタブレット) で先進認証を有効にするには、次のレジストリ キーを設定する必要があります。先進認証を有効にするデバイスごとに、次のキーを設定する必要があります。

|**レジストリ キー**|**型**|**値** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |

[Skype for Businessで先進認証 (ADAL) を使用する方法](./hybrid-modern-auth-overview.md)に関する記事を参照して、Skype for Businessでの動作について説明します。

Office 2016 および Office 2019 クライアントでは、既定で最新の認証がサポートされており、クライアントがこれらの新しいフローを使用するためのアクションは必要ありません。 ただし、レガシ認証を使用するには、明示的なアクションが必要です。

次のリンクをクリックして、2013 Office 年、Office 2016 年、Office 2019 クライアント認証をMicrosoft 365 サービスと連携させる方法を確認します。最新の認証が有効になっているかどうかに応じて確認できます。

- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)

- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)

- [Skype for Business Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)

<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

次の表は、Office 2013、Office 2016、Office 2019 クライアント アプリが先進認証の有無にかかわらずExchange Onlineに接続するときの認証動作を示しています。

|Office クライアント アプリのバージョン****|レジストリ キーが存在しますか?****|最新の認証をオンにしますか?****|テナントに対して先進認証が有効になっている認証動作 (既定値)****|テナントの先進認証がオフになっている認証動作****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |いいえ <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |はい  <br/> |Outlook 2013、2016、または 2019 で先進認証を強制します。 <br/> [詳細情報](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Outlook クライアント内で先進認証を強制します。<br/> |
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL=0  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2016  <br/> |いいえ <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |はい  <br/> |2013、2016、または 2019 で先進認証を強制します。 <br/> [詳細情報](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Outlook クライアント内で先進認証を強制します。<br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL=0  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |基本認証  <br/> |基本認証  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、基本認証が使用されます。 テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |

<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

次の表では、Office 2013、Office 2016、Office 2019 クライアント アプリが最新の認証を使用してSharePoint Online に接続するときの認証動作について説明します。

|Office クライアント アプリのバージョン****|レジストリ キーが存在しますか?****|最新の認証をオンにしますか?****|テナントに対して先進認証が有効になっている認証動作 (既定値)****|テナントの先進認証がオフになっている認証動作****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |先進認証のみ。  <br/> |接続できない。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証のみ。  <br/> |接続できない。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |先進認証のみ。  <br/> |接続できない。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証のみ。  <br/> |接続できない。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証のみ。  <br/> |接続できない。  <br/> |

### <a name="skype-for-business-online"></a>Skype for Business Online
<a name="BK_SFBO"> </a>

次の表では、Office 2013、Office 2016、Office 2019 クライアント アプリが最新の認証を使用してSkype for Business Online に接続するときの認証動作について説明します。

|Office クライアント アプリのバージョン****|レジストリ キーが存在しますか?****|最新の認証をオンにしますか?****|テナントに対して先進認証が有効になっている認証動作****|テナントの先進認証がオフになっている認証動作 (既定値)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2019  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2016  <br/> |いいえ、または EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |
|Office 2016  <br/> |はい、EnableADAL = 0  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |いいえ  <br/> |いいえ  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |
|Office 2013  <br/> |はい、EnableADAL = 1  <br/> |はい  <br/> |先進認証が最初に試行されます。 サーバーが最新の認証接続を拒否した場合は、Microsoft Online サインイン アシスタントが使用されます。 Skype for Business Online テナントが有効になっていない場合、サーバーは先進認証を拒否します。  <br/> |Microsoft Online サインイン アシスタントのみ。  <br/> |

## <a name="see-also"></a>関連項目

[Windows デバイスの Office 2013 の先進認証を有効にする](../admin/security-and-compliance/enable-modern-authentication.md)

[Microsoft 365 の多要素認証](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[多要素認証を使用してMicrosoft 365にサインインする](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)