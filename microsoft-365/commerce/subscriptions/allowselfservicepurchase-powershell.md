---
title: MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell コマンドレットを使用してセルフサービス購入をオンまたはオフにする方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 07/16/2021
ms.openlocfilehash: 77cb1c753db22929ea2c3d14226a3927e6406b89
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461365"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する

**MSCommerce** PowerShell モジュールが [PowerShell ギャラリーで利用できます](https://aka.ms/allowselfservicepurchase-powershell-gallery)。 このモジュールには **、組織内のユーザー** がセルフサービス購入を行えるかどうかを制御できる **AllowSelfServicePurchase** の PolicyID パラメーター値が含まれています。

**MSCommerce PowerShell** モジュールを使用すると、次の目的で使用できます。

- **AllowSelfServicePurchase** パラメーター値の既定の状態を表示する (有効または無効のかどうか)
- 該当する製品の一覧とセルフサービス購入が有効か無効かを表示する
- 特定の製品の現在の設定を表示または変更して、有効または無効にする

## <a name="requirements"></a>要件

**MSCommerce PowerShell モジュール** を使用するには、次が必要です。

- デバイスWindows 10デバイス
- PowerShell 5 以下。 現在、PowerShell 6.x/7.x は、このモジュールではサポートされていません。
- デバイスの管理者のアクセス許可
- テナントのグローバルまたは課金管理者の役割

## <a name="install-the-mscommerce-powershell-module"></a>MSCommerce PowerShell モジュールのインストール

**MSCommerce** PowerShell モジュールは、Windows 10デバイスに 1 回インストールし、開始する各 PowerShell セッションにインポートします。 **PowerShell ギャラリーから MSCommerce** [PowerShell モジュールをダウンロードします](https://aka.ms/allowselfservicepurchase-powershell-gallery)。

**PowerShellGet を使用して MSCommerce** PowerShell モジュールをインストール **するには、** 次のコマンドを実行します。

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MsCommerce を PowerShell セッションにインポートする

モジュールをデバイスにインストールしたWindows 10、開始する各 PowerShell セッションにモジュールをインポートします。 PowerShell セッションにインポートするには、次のコマンドを実行します。

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Connectを使用して MSCommerce にアクセスする

資格情報を使用して PowerShell モジュールに接続するには、次のコマンドを実行します。

```powershell
Connect-MSCommerce
```

このコマンドは、現在の PowerShell セッションを新しいテナントAzure Active Directoryします。 接続するテナントのユーザー名とパスワードを求めるメッセージが表示されます。 資格情報に対して多要素認証が有効になっている場合は、対話型オプションを使用してログインします。

## <a name="view-details-for-allowselfservicepurchase"></a>AllowSelfServicePurchase の詳細を表示する

組織に基づいて **AllowSelfServicePurchase** パラメーター値と既定の状態の説明を表示するには、次のコマンドを実行します。

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>セルフサービス購入製品とその状態の一覧を表示する

利用可能なすべてのセルフサービス購入製品の一覧とそれぞれの状態を表示するには、次のコマンドを実行します。

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

次の表に、使用可能な製品とその **ProductId を示します**。

| 製品 | ProductId |
|-----------------------------|--------------|
| Power Apps 1 人あたりのユーザー数 | CFQ7TTC0KP0P |
| Power Automate 1 人あたりのユーザー数 | CFQ7TTC0KP0N |
| Power AutomateRPA | CFQ7TTC0KXG6  |
| Power BI Premium (スタンドアロン) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1 | CFQ7TTC0KXND |
| Project Plan 3 | CFQ7TTC0KXNC |
| Visio Plan 1 | CFQ7TTC0KXN9 |
| Visio プラン 2 | CFQ7TTC0KXN8 |
| Windows 365 Enterprise | CFQ7TTC0HHS9 |
| Windows 365 Business | CFQ7TTC0J203 |
| Windows 365 Business with Windows ハイブリッド 特典 | CFQ7TTC0HX99 |
## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>AllowSelfServicePurchase の状態を表示または設定する

セルフサービス購入で使用できる製品の一覧を表示した後、特定の製品の設定を表示または変更できます。

特定の製品のポリシー設定を取得するには、次のコマンドを実行します。

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

特定の製品のポリシー設定を有効にするには、次のコマンドを実行します。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

特定の製品のポリシー設定を無効にするには、次のコマンドを実行します。

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>AllowSelfServicePurchase を無効にするスクリプトの例

次の例では **、MSCommerce** モジュールをインポートし、アカウントでサインインし、Power Automate の **ProductId** を取得し、その製品の **AllowSelfServicePurchase** を無効にする方法について説明します。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="problem"></a>問題

次のエラー メッセージが表示されます。

> HandleError : PolicyId 'AllowSelfServicePurchase', ErrorMessage - 基になる接続が閉じられました: 送信時に予期しないエラーが発生しました。

これは、トランスポート層セキュリティ (TLS) の古いバージョンが原因である可能性があります。 このサービスを接続するには、TLS 1.2 以上を使用する必要があります。

### <a name="solution"></a>ソリューション

TLS 1.2 へのアップグレード: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>関連コンテンツ

[セルフサービス購入の管理 (管理者) (](manage-self-service-purchases-admins.md) 記事)

[セルフサービス購入に関する FAQ](self-service-purchase-faq.yml) (記事)
