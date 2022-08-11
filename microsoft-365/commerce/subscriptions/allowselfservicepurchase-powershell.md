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
ms.date: 08/09/2022
ms.openlocfilehash: 080b12672607301b9dcc9977c1c93ad9b48d43cd
ms.sourcegitcommit: f72ea75c6d5c1bca0e0ed8fd228d3a84c6104361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67301902"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する

[PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery) で **MSCommerce** PowerShell モジュールが利用できるようになりました。 このモジュールには、組織内のユーザーがセルフサービスで購入できるかどうかを制御できる **AllowSelfServicePurchase** 向けの **PolicyID** パラメーター値が含まれます。

**MSCommerce** PowerShell モジュールを使用すると以下のことができます。

- **AllowSelfServicePurchase** パラメーター値の既定の状態 (有効、無効、または支払い方法のない試用を許可するかどうか) を表示する
- 該当する製品の一覧と、セルフサービス購入が有効か無効か、または支払い方法なしで試用版を許可するかを表示する
- 特定の製品の現在の設定を表示または変更し、有効または無効にする
- 支払い方法のない試用版の設定を表示または変更する

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
| ユーザーごとの Power Apps* | CFQ7TTC0LH2H |
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
| Microsoft 365 F3 | CFQ7TTC0LH05 |
| Dynamics 365 Marketing | CFQ7TTC0LH3N |
| Dynamics 365 Marketing Attach | CFQ7TTC0LHWP | 
| Dynamics 365 Marketing の追加アプリケーション | CFQ7TTC0LHVK |
| Dynamics 365 Marketing Additional Non-Prod Application | CFQ7TTC0LHWM |

*これらの ID は変更されています。 以前に古い ID を使用して製品をブロックした場合、新しい ID を使用して製品は自動的にブロックされます。 追加の作業は必要ありません。

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>AllowSelfServicePurchase の状態を表示または設定する

**AllowSelfServicePurchase** の **Value** パラメーターを設定して、ユーザーがセルフサービスでの購入を許可または禁止することができます。 **OnlyTrialsWithoutPaymentMethod** 値を使用して、ユーザーが承認された製品の一覧から製品を試すこともできます。 ユーザーは、 **AllowSelfServicePurchase** が有効になっている場合にのみ、試用版が終了した後に製品を購入できます。

**OnlyRialsWithoutPaymentMethod** 値を使用すると、一時的な試用版を許可しながら、購入をブロックできます。

次の表では、 **Value** パラメーターの設定について説明します。

| **設定** | **影響** |
|---|---|
| Enabled | ユーザーは、セルフサービスでの購入を行い、製品の試用版を取得できます。 |
| OnlyRialsWithoutPaymentMethod | ユーザーはセルフサービスで購入することはできませんが、製品の試用版を取得できます。 試用版の有効期限が切れた後、完全版を購入することはできません。 |
| 無効 | ユーザーは、セルフサービスで購入したり、製品の試用版を取得したりすることはできません。 |

特定の製品のポリシー設定を取得するには、以下のコマンドを実行します。

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

特定の製品のポリシー設定を有効にするには、以下のコマンドを実行します。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Value "Enabled"
```

特定の製品のポリシー設定を無効にするには、以下のコマンドを実行します。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Value "Disabled"
```

ユーザーが支払い方法なしで特定の製品を試すことができるようにするには、次のコマンドを実行します。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Value "OnlyTrialsWithoutPaymentMethod" 
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>AllowSelfServicePurchase を無効にするスクリプト例

次の例では、 **MSCommerce** モジュールをインポートし、アカウントでサインインし、ユーザーごとに **ProductId** for Power Automate を取得し、その製品の **AllowSelfServicePurchase** を無効にする方法について説明します。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate per user'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Value "Disabled"
```

製品に複数の値がある場合は、次の例に示すように、値ごとに個別にコマンドを実行できます。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[0].ProductID -Value "Disabled"
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[1].ProductID -Value "Disabled"
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

[セルフサービス購入の管理 (管理)](manage-self-service-purchases-admins.md) (記事)\
[セルフサービス購入に関するよくあるご質問](self-service-purchase-faq.yml) (記事)
