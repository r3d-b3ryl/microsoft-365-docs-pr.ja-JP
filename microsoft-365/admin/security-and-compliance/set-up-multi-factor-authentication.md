---
title: Office 365 ユーザー用の多要素認証を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: セキュリティの既定値を使用して Office 365 ユーザー用の多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 914d01bf2f045c6752aba4f2df3a204c6a21d09c
ms.sourcegitcommit: 4d4d27a49eb258dc560439ca4baf61ebb9c1eff3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2020
ms.locfileid: "43075610"
---
# <a name="set-up-multi-factor-authentication"></a>多要素認証をセットアップする
  
> [!IMPORTANT]
> 2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、MFA を予期せずに要求されると、サブスクリプションに対して[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。

新しい法人向け Office 365 または Microsoft 365 Business のすべてのサブスクリプションは、自動的にセキュリティの既定値が有効になっています。 つまり、すべてのユーザーが多要素認証 (MFA) を設定し、モバイル デバイスに Authenticator アプリをインストールする必要があります。 詳細については、「[Office 365 で 2 段階認証をセットアップする](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。  

サインインするたびに追加の認証を実行するには、次にあげる 9 個の管理者ロールが必要になります。
- グローバル管理者
- SharePoint 管理者
- Exchange 管理者
- 条件付きアクセス管理者
- セキュリティ管理者
- ヘルプデスク管理者/パスワード管理者
- 課金管理者
- ユーザー管理者
- 認証管理者

他のすべてのユーザーは、必要に応じて追加認証を求められます。 詳細については、「[セキュリティの既定値とは](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。

> [!NOTE]
> 多要素認証を設定または変更するには、Office 365 のグローバル管理者である必要があります。 <br><br>
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

以前にベースライン ポリシーを使用して MFA をセットアップしている場合は、[それらをオフにして、セキュリティの既定値をオンにする必要があります](#move-from-baseline-policies-to-security-defaults)。 ただし、Microsoft 365 Business を所有している場合、またはサブスクリプションに [Azure Active Directory Premium 1、または Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) が含まれている場合は、[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) ポリシーを設定することもできます。 条件付きアクセスポリシーを使用するには、[先進認証](#enable-modern-authentication-for-your-organization)が有効になっていることを確認する必要があります。

> [!TIP]
> ユーザーに Authenticator アプリをセットアップする方法を説明するには、「[Office 365 で Microsoft Authenticator を使用する](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)」をご覧ください。

## <a name="manage-security-defaults"></a>セキュリティの既定値の管理

1. グローバル管理者の資格情報を使用して、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)にサインインします。
2. [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。

3. ページの下部で、[**セキュリティの既定値の管理**] を選択します。
4. セキュリティの規定値を有効にするには [**はい**] を選択し、セキュリティの規定値を無効にするには [**いいえ**] を選択します。

## <a name="move-from-baseline-policies-to-security-defaults"></a>ベースライン ポリシーからセキュリティの既定値に移行する

1. [管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で、[**設定**] を選択します。

2. [**サインインとセキュリティ**] の横の [**サインインのセキュリティを強化する**] で [**表示**] を選択します。

3. [**サインインのセキュリティを強化する**] で、[**管理**] を選択します。 

4. [**Azure portal 条件付きアクセス - ポリシー**] ページで、[**オン**]になっているベースライン ポリシーをそれぞれ選び、[**オフ**]に設定します。
5. [[Azure Active Directory のプロパティ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)] ページにアクセスします。
6. ページの下部で、[**セキュリティの既定値の管理**]を選択し、[**セキュリティの既定値の有効化**] ウィンドウで、[**Enable Security defaults (セキュリティの規定値を有効にする)**] トグルを [**はい**] に設定します。 

## <a name="enable-modern-authentication-for-your-organization"></a>組織の先進認証を有効にする

Office 2016 のクライアント アプリケーションはすべて、Active Directory Authentication Library (ADAL) を使用して MFA をサポートします。 つまり、Office 2016 クライアントでは、アプリ パスワードは必要ありません。 ただし、Office 365 サブスクリプションが ADAL または先進認証に対して有効になっていることを確認する必要があります。

1. 先進認証を有効にするには、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で **[設定]** \> **[設定]** の順に選択し、次に **[サービス]** タブのリストから **[先進認証]** を選択します。

2. [**先進認証**] パネルの [**先進認証を有効にする**] チェックボックスをオンにします。 

    ![チェックボックスをオンにした状態の [先進認証] パネル](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> 2017 年 8 月に、Skype for Business Online と Exchange Online を含むすべての新しい Office 365 テナントには、既定で先進認証が有効になっています。 Skype for Business Online の先進認証状態を確認するには、グローバル管理者の資格情報を使用して Skype for Business Online PowerShell を使用します。 Get-CsOAuthConfiguration を実行して、-ClientADALAuthOverride の出力を確認します。 -ClientADALAuthOverride が「許可」の場合は、先進認証が有効になります。
Exchange Online の MA 状態を確認するには、「[Exchange Online で先進認証を有効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)」を参照してください。

## <a name="related-articles"></a>関連記事

[Office 365とMicrosoft 365 Businessプランを安全にする10の方法](secure-your-business-data.md)

[Windows デバイスの Office 2013 の先進認証を有効にする](enable-modern-authentication.md)
