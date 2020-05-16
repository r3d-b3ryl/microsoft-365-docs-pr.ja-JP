---
title: ユーザーの多要素認証を設定する
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
description: セキュリティの既定値を使用してユーザーに多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262377"
---
# <a name="set-up-multi-factor-authentication"></a>多要素認証をセットアップする
  
> [!IMPORTANT]
> 2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、多要素認証 (MFA) を予期せずに要求されると、サブスクリプションに対して[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。

すべての新しい Microsoft 365 サブスクリプションの[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。 これは、すべてのユーザーが多要素認証 (MFA) を設定し、モバイルデバイスに Microsoft Authenticator アプリをインストールする必要があることを意味します。 詳細については、「 [Microsoft 365 アカウントの MFA を設定する](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。

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

他のすべてのユーザーは、必要に応じて追加認証を求められます。

> [!NOTE]
> MFA を設定または変更するには、グローバル管理者である必要があります。 <br><br>
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

以前にベースラインポリシーを使用して MFA をセットアップしている場合は、[セキュリティの既定値を有効にするために、これらの機能をオフにする必要があり](#move-from-baseline-policies-to-security-defaults)ます。 ただし、Microsoft 365 Business またはサブスクリプションに[Azure Active Directory Premium P1 または Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)が搭載されている場合は、[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシーを設定することもできます。 条件付きアクセスポリシーを使用するには、セキュリティの既定値を無効にし、[先進認証](#enable-modern-authentication-for-your-organization)が有効になっていることを確認する必要があります。

> [!TIP]
> Microsoft Authenticator アプリをセットアップする方法をユーザーに説明するには、「 [office 365 で Microsoft authenticator を使用](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)する」を参照してください。

## <a name="manage-security-defaults"></a>セキュリティの既定値の管理

1. グローバル管理者の資格情報を使用して、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)にサインインします。
2. [ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。
3. ページの下部で、[**セキュリティの既定値の管理**] を選択します。
4. [**はい]** を選択して**セキュリティの既定**値を有効にし、セキュリティの既定値を無効にして [**保存**] を選択します。

## <a name="move-from-baseline-policies-to-security-defaults"></a>ベースライン ポリシーからセキュリティの既定値に移行する

1. [[条件付きアクセスポリシー] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)に移動します。
2. 有効になっているそれぞれ**の**ベースラインポリシーを選択し、[**ポリシーの有効化**] を [**オフ**] に設定します。
3. [ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。
4. ページの下部にある [セキュリティの**既定の管理**] をクリックし、[**セキュリティ**の既定値を有効にする] ウィンドウで、[**セキュリティの既定値を有効**にする] を [**はい**] に設定して、[**保存**] を選択します。 

## <a name="enable-modern-authentication-for-your-organization"></a>組織の先進認証を有効にする

Office 2016 のクライアント アプリケーションはすべて、Active Directory Authentication Library (ADAL) を使用して MFA をサポートします。 つまり、Office 2016 クライアントでは、アプリ パスワードは必要ありません。 詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords)を参照してください。

ただし、Microsoft 365 サブスクリプションが ADAL に対して有効になっていること、または先進認証が有効になっていることを確認する必要があります。

1. モダン認証を有効にするには、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)から [**設定**] [ \> **組織設定**] を選択し、[**サービス**] タブでリストから [**モダン認証**] を選択します。

2. **モダン認証**パネルの [**モダン認証を有効にする (推奨)** ] チェックボックスをオンにし、[**変更の保存**] を選択します。 

    ![チェックボックスをオンにした状態の [先進認証] パネル](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> 2017年8月現在、Skype for Business online と Exchange online を含むすべての新しい Microsoft 365 サブスクリプションでは、先進認証が既定で有効になっています。 Skype for Business Online の先進認証状態を確認するには、グローバル管理者の資格情報を使用して Skype for Business Online PowerShell を使用します。 Get-CsOAuthConfiguration を実行して、-ClientADALAuthOverride の出力を確認します。 -ClientADALAuthOverride が「許可」の場合は、先進認証が有効になります。
Exchange Online の MA 状態を確認するには、「[Exchange Online で先進認証を有効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)」を参照してください。

## <a name="related-articles"></a>関連記事

[Microsoft 365 for business プランをセキュリティで保護するための10位の方法](secure-your-business-data.md)

[Windows デバイスの Office 2013 の先進認証を有効にする](enable-modern-authentication.md)
