---
title: MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: ''
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_ssp
- AdminSurgePortfolio
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell コマンドレットを使用して、セルフサービスでの購入のオンまたはオフを切り替える方法をご紹介します。
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 12/15/2021
ms.openlocfilehash: a3800f82386fafe509d9bdabb25cd91422cf058d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315723"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する

[PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery) で **MSCommerce** PowerShell モジュールが利用できるようになりました。 このモジュールには、組織内のユーザーがセルフサービスで購入できるかどうかを制御できる **AllowSelfServicePurchase** 向けの **PolicyID** パラメーター値が含まれます。

**MSCommerce** PowerShell モジュールを使用すると以下のことができます。

- **AllowSelfServicePurchase** パラメーター値の既定の状態 (有効または無効) を表示します。
- 利用可能な製品の一覧およびセルフサービス購入の有効または無効を表示する
- 特定の製品の現在の設定を表示または変更し、有効または無効にする

## <a name="requirements"></a>要件

**MSCommerce** PowerShell モジュールを使用するには、以下の物が必要です。

- Windows 10 デバイス
- PowerShell 5 以下。 現在、PowerShell 6.x/7.x はこのモジュールではサポートされていません。
- デバイスの管理者権限
- テナントのグローバル管理者または課金管理者ロール

## <a name="install-the-mscommerce-powershell-module"></a>MSCommerce PowerShell モジュールのインストール

**MSCommerce** PowerShell モジュールを Windows 10 デバイスに一度インストールして、起動する各 PowerShell セッションにインポートします。 [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery) で **MSCommerce** PowerShell モジュールをダウンロードします。

**PowerShellGet** を使用して **MSCommerce** PowerShell モジュールをインストールするには、次のコマンドを実行します。

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MSCommerce を PowerShell セッションにインポートする

モジュールを Windows 10 デバイスに一度インストールした後、起動する各 PowerShell セッションにインポートします。 PowerShell セッションにインポートするには、次のコマンドを実行します。

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>自分の資格情報を使用して MSCommerce に接続する

自分の認証情報を使用して PowerShell モジュールに接続するには、次のコマンドを実行します。

```powershell
Connect-MSCommerce
```

このコマンドでは、現在の PowerShell セッションを Azure Active Directory テナントに接続します。 このコマンドでは、接続するテナントのユーザー名とパスワードの入力を求められます。 資格情報に多要素認証が有効になっている場合は、対話型のオプションを使用してログインします。

## <a name="view-details-for-allowselfservicepurchase"></a>AllowSelfServicePurchase の詳細を表示する

組織に基づく **AllowSelfServicePurchase** パラメーター値の説明と既定の状態を表示するには、次のコマンドを実行します。

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>セルフサービス購入製品の一覧とその状態を表示する

利用可能なすべてのセルフサービス購入製品の一覧と各製品の状態を表示するには、次のコマンドを実行します。

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

以下のテーブルは、利用可能な製品とその **ProductId** を一覧表示しています。

| 製品 | ProductId |
|-----------------------------|--------------|
| ユーザーごとの Power Apps | CFQ7TTC0KP0P |
| ユーザーごとの Power Automate | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (スタンドアロン) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1* | CFQ7TTC0HDB1 |
| Project Plan 3* | CFQ7TTC0HDB0 |
| Visio Plan 1* | CFQ7TTC0HD33 |
| Visio Plan 2* | CFQ7TTC0HD32 |
| Windows 365 Enterprise | CFQ7TTC0HHS9 |
| Windows 365 Business | CFQ7TTC0J203 |
| Windows ハイブリッド特典付き Windows 365 Business | CFQ7TTC0HX99 |

*これらの ID は変更されています。 以前に古い ID を使用して製品をブロックした場合、新しい ID を使用して製品は自動的にブロックされます。 追加の作業は必要ありません。

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>AllowSelfServicePurchase の状態を表示または設定する

セルフサービスで購入可能な製品の一覧を表示した後、特定の製品の設定を確認したり変更したりすることができます。

特定の製品のポリシー設定を取得するには、以下のコマンドを実行します。

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

特定の製品のポリシー設定を有効にするには、以下のコマンドを実行します。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

特定の製品のポリシー設定を無効にするには、以下のコマンドを実行します。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>AllowSelfServicePurchase を無効にするスクリプト例

以下の例では、**MSCommerce** モジュールをインポートし、自分のアカウントでサインインし、Power Automate の **ProductId** を取得し、その製品の **AllowSelfServicePurchase** を無効にする方法について説明しています。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

製品に複数の値がある場合は、次の例に示すように、値ごとに個別にコマンドを実行できます。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[0].ProductID -Enabled $false
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[1].ProductID -Enabled $false
```


## <a name="troubleshooting"></a>トラブルシューティング

### <a name="problem"></a>問題

次のようなエラー メッセージが表示されます。

> HandleError: PolicyId 'AllowSelfServicePurchase' でポリシーを取得できませんでした、ErrorMessage - 基になる接続が閉じられました: 送信で予期しないエラーが発生しました。

これは、トランスポート層セキュリティ (TLS) の以前のバージョンが原因である可能性があります。 このサービスに接続するには、TLS 1.2 以降を使用する必要があります。

### <a name="solution"></a>ソリューション

TLS 1.2 にアップグレードします。 次の構文は、ServicePointManager セキュリティ プロトコルを TLS1.2 に更新します。

```powershell
 [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.SecurityProtocolType]::Tls12
```

詳細については、「 [TLS 1.2 を有効にする方法](/mem/configmgr/core/plan-design/security/enable-tls-1-2)」を参照してください。

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>関連コンテンツ

[セルフサービスによる購入を管理する (管理者)](manage-self-service-purchases-admins.md) (記事)

[セルフサービス購入に関するよくあるご質問](self-service-purchase-faq.yml) (記事)
