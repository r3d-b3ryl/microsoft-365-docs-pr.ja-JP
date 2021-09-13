---
title: DAP パートナー向けデータを使用して顧客Windows PowerShellレポート データを取得する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 概要:Microsoft Exchange Online用のリモートWindows PowerShellを使用して、個々の顧客テナントからレポートを取得します。
ms.openlocfilehash: ee9639ae8d5b77443dcfc119f34bc378992920ae
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215703"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>委任アクセス許可 (DAP) パートナー用 Windows PowerShell を使用して顧客のテナント レポート データを取得する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

個々の顧客Windows PowerShellからMicrosoft Exchange Onlineレポートを取得するには、リモート サーバーを使用します。

シンジケーションとクラウド ソリューション プロバイダー (CSP) パートナーは、PowerShell のリモート サーバー経由で顧客テナント レポートを直接構成するWindows PowerShellアクセスExchange Onlineできます。 これにより、パートナーはレポートのデータを収集および保存してから、その他の操作を実行できます。 リモート接続を開いた後、顧客テナンシーに関するレポート データを取得することは、顧客テナンシーに対してなんらかのコマンドレットを実行することと同じです。

この記事では、リモート Windows PowerShellをExchange Online単一の顧客テナントに接続し、レポートを取得します。 既定では、Windows PowerShell は複数の顧客テナンシーからレポート データを集約することをサポートしていません。 この手順で取得するレポートは、接続先の  _DelegatedOrg_ のレポートのみです。

## <a name="before-you-begin"></a>始める前に

- Exchange Online テナントへの接続は、リモートの Windows PowerShell を使用して行う必要があります。手順については、「[委任アクセス許可 (DAP) パートナー用リモート Windows PowerShell で Exchange Online テナントに接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

## <a name="run-the-get-stalemailboxreport-sample"></a>Get-StaleMailboxReport のサンプルを実行する

Exchange Online へのリモート セッションを開いた後、このコマンドを実行して、日付範囲が 03/25/2015 ～ 03/31/2015 の **Get-StaleMailboxReport** を取得します。

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Exchange Online、Lync Online、および SharePoint Online には使用できるその他多数のレポート コマンドレットだけでなく、使用できるその他のメッセージ追跡用コマンドレットもあります。使用可能なレポート コマンドレットと Office 365 レポート Web サービスの詳細については、次のセクションのトピックを参照してください。

## <a name="see-also"></a>関連項目

[Office 365 レポート Web サービス](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Get-CsClientDeviceDetailReport](/powershell/module/exchange/get-csclientdevicedetailreport)

[パートナーのヘルプ](https://go.microsoft.com/fwlink/p/?LinkID=533477)
