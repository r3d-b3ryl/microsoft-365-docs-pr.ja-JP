---
title: MSCommerce PowerShell モジュールで AllowSelfServicePurchase を使用する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell コマンドレットを使用して、セルフサービスの購入をオンまたはオフにする方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653715"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>MSCommerce PowerShell モジュールで AllowSelfServicePurchase を使用する

[Powershell ギャラリー](https://aka.ms/allowselfservicepurchase-powershell-gallery)で**MSCommerce** powershell モジュールを使用できるようになりました。 このモジュールには、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御できる、 **Allowselfservicepurchase**の**policyid**パラメーターの値が含まれています。

**MSCommerce** PowerShell モジュールを使用して、次のことを行うことができます。

- **Allowselfservicepurchase**パラメーター値の既定の状態を表示する (有効または無効)
- 適用可能な製品の一覧、およびセルフサービス購入が有効か無効かを表示する
- 特定の製品の現在の設定を表示または変更して、有効にするか無効にするかを指定します。

## <a name="requirements"></a>要件

**MSCommerce** PowerShell モジュールを使用するには、次のものが必要です。

- Windows 10 デバイス
- デバイスに対する管理者のアクセス許可
- テナントのグローバルまたは課金管理者の役割

## <a name="install-the-mscommerce-powershell-module"></a>MSCommerce PowerShell モジュールをインストールする

**MSCommerce** powershell モジュールを Windows 10 デバイスに1回インストールしてから、開始する各 powershell セッションにインポートします。 [Powershell ギャラリー](https://aka.ms/allowselfservicepurchase-powershell-gallery)から**MSCommerce** powershell モジュールをダウンロードします。

**PowerShellGet**を使用して**MSCommerce** PowerShell モジュールをインストールするには、次のコマンドを実行します。

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>PowerShell セッションに MSCommerce をインポートする

Windows 10 デバイスにモジュールをインストールしたら、開始する各 PowerShell セッションにモジュールをインポートします。 PowerShell セッションにインポートするには、次のコマンドを実行します。

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>資格情報を使用して MSCommerce に接続する

資格情報を使用して PowerShell モジュールに接続するには、次のコマンドを実行します。

```powershell
Connect-MSCommerce
```

このコマンドは、現在の PowerShell セッションを Azure Active Directory テナントに接続します。 このコマンドを実行すると、接続先のテナントのユーザー名とパスワードを入力するように求められます。 資格情報に対して多要素認証が有効になっている場合は、interactive オプションを使用してログインします。

## <a name="view-details-for-allowselfservicepurchase"></a>AllowSelfServicePurchase の詳細を表示する

組織に基づいて**Allowselfservicepurchase**パラメーター値と既定の状態の説明を表示するには、次のコマンドを実行します。

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>セルフサービス購入製品とその状態の一覧を表示する

利用可能なすべてのセルフサービス購入製品と各の状態の一覧を表示するには、次のコマンドを実行します。

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

次の表に、使用可能な製品とその**ProductId**を示します。

| 製品 | △ |
|-----------------------------|--------------|
| ユーザーあたりの電源アプリ | CFQ7TTC0KP0P |
| ユーザーごとの電源自動化 | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| プロジェクト計画1 | CFQ7TTC0KXND |
| プロジェクト計画3 | CFQ7TTC0KXNC |
| Visio プラン1 | CFQ7TTC0KXN9 |
| Visio プラン2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>AllowSelfServicePurchase の状態を表示または設定する

セルフサービス購入可能な製品の一覧を表示した後、特定の製品の設定を表示または変更できます。

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

次の例では、 **MSCommerce**モジュールをインポートする方法、自分のアカウントでサインインする方法、および製品の電源自動化のために**ProductId**を取得する方法、およびその製品の**allowselfservicepurchase**を無効にする方法について順を追って説明します。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="problem"></a>問題

次のエラーメッセージが表示されます。

> HandleError: ポリシー Id ' AllowSelfServicePurchase '、ErrorMessage-基になる接続が閉じられました。送信で予期しないエラーが発生しました。

これは、トランスポート層セキュリティ (TLS) の古いバージョンが原因である可能性があります。 このサービスを接続するには、TLS 1.2 以上を使用する必要があります。

### <a name="solution"></a>ソリューション

TLS 1.2 にアップグレードします。[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
