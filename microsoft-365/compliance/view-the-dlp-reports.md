---
title: データ損失防止のレポートの表示
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Office 365の DLP レポートを使用して、DLP ポリシーの一致、オーバーライド、または誤検知の数を表示し、時間の経過と共に増加または減少の傾向を確認します。
ms.openlocfilehash: 01064662e0af82ec98837c8518172bcfeffbaa96
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753542"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>データ損失防止のレポートの表示

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purviewデータ損失防止 (DLP) ポリシーを作成したら、意図したとおりに動作していることを確認し、準拠を維持するのに役立ちます。 Microsoft Purview コンプライアンス ポータルの DLP レポートを使用すると、次をすばやく表示できます。
  
- **DLP ポリシーの一致** このレポートには、時間の経過と共に一致する DLP ポリシーの数が表示されます。 レポートは、日付、場所、ポリシー、またはアクションによってフィルター処理できます。 このレポートを使用すると、以下のことを行えます。 
    
  - テスト モードで実行しているときに、DLP ポリシーの調整や絞り込みができる。 コンテンツと一致する特定のルールを見ることができます。
    
  - 特定の期間に絞り込み、スパイクや傾向の理由を理解します。
    
  - 組織の DLP ポリシーに違反するビジネス プロセスを検出します。
    
  - コンテンツに適用されているアクションを確認することで、DLP ポリシーのビジネスへの影響を理解します。
    
  - 特定の DLP ポリシーに関する一致箇所を表示することによって、そのポリシーのコンプライアンス遵守を確認します。
    
  - 組織内のインシデントに貢献している上位ユーザーとリピート ユーザーの一覧を表示します。
    
  - 組織内の機密情報の種類の上位一覧を表示します。
    
- **DLP インシデント** このレポートには、ポリシーの一致レポートなど、時間の経過と共にポリシーが一致することも示されます。 ただし、ポリシーの一致レポートには、ルール レベルでの一致が表示されます。たとえば、メールが 3 つの異なるルールに一致した場合、ポリシー一致レポートには 3 つの異なる行項目が表示されます。 これに対し、インシデント レポートにはアイテム レベルでの一致が表示されます。たとえば、電子メールが 3 つの異なるルールに一致した場合、インシデント レポートには、そのコンテンツの 1 つの行項目が表示されます。 
    
  レポート数は集計方法が異なるため、ポリシー一致レポートは、特定のルールとの一致を識別し、DLP ポリシーを微調整する場合に適しています。 インシデント レポートは、DLP ポリシーで問題となる特定のコンテンツを特定するのに適しています。
    
- **DLP の誤検知とオーバーライド** DLP ポリシーでユーザーがオーバーライドしたり、誤検知を報告したりできる場合、このレポートには、時間の経過に伴うこのようなインスタンスの数が表示されます。 レポートは、日付、場所、ポリシー、またはポリシーによってフィルター処理できます。 このレポートを使用すると、以下のことを行えます。 
    
  - 多くの偽陽性が発生しているポリシーを確認し、DLP ポリシーの調整や絞り込みをします。
    
  - ユーザーがポリシーを上書きしてポリシーのヒントを解決するときに送信する正当な理由を表示します。
    
  - ユーザーによる多くの上書きが行われることによって、DLP ポリシーと有効なビジネスプロセスとの競合を検出します。
    
すべての DLP レポートでは、最新の 4 か月間のデータを表示できます。 最新のデータは、レポートに表示されるまで最大で 24 時間かかることがあります。
  
これらのレポートは、Microsoft Purview コンプライアンス ポータル \> **レポート** \> **ダッシュボード** にあります。
  
![DLP ポリシーはレポートと一致します。](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>オーバーライドのためにユーザーによって送信された理由を表示する

DLP ポリシーでユーザーがそれを上書きすることを許可している場合は、誤検知および上書きレポートを使用して、ポリシーのヒントでユーザーが送信したテキストを表示できます。
  
![DLP の誤検知と上書きレポートの詳細の正当な理由フィールド。](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>分析情報と推奨事項に関するアクションを実行する

レポートには分析情報と推奨事項が表示され、赤い警告アイコンをクリックして潜在的な問題の詳細を表示し、可能な修復アクションを実行できます。
  
![分析情報アイコンをクリックすると、実行する詳細とアクションが表示されます。](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>DLP レポートのアクセス許可

セキュリティ & コンプライアンス センターで DLP レポートを表示するには、次の情報を割り当てる必要があります。

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>の **セキュリティ 閲覧者** ロール。 既定では、このロールは、Exchange管理センターの組織の管理とセキュリティ 閲覧者の役割グループに割り当てられます。

- セキュリティ **& コンプライアンス センターの表示専用 DLP コンプライアンス管理** ロール。 既定では、このロールは、セキュリティ & コンプライアンス センターのコンプライアンス管理者、組織管理、セキュリティ管理者、およびセキュリティ 閲覧者の役割グループに割り当てられます。

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>の **表示専用受信者** ロール。 既定では、このロールは、Exchange管理センターのコンプライアンス管理、組織管理、View-Only組織管理の役割グループに割り当てられます。

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>DLP レポートのコマンドレットを見つける

Microsoft Purview コンプライアンス ポータルにほとんどのコマンドレットを使用するには、次の手順を実行する必要があります。
  
1. [リモート PowerShell を使用してMicrosoft Purview コンプライアンス ポータルにConnectする](/powershell/exchange/connect-to-scc-powershell)
    
2. これらの[セキュリティ &amp; コンプライアンス センターコマンドレット](/powershell/exchange/exchange-online-powershell)のいずれかを使用する
    
ただし、DLP レポートは、Exchange Online を含む Office 365 全体からデータを取り込む必要があります。 このため、DLP レポートのコマンドレットは、powershell ではなくExchange Online Powershell で使用Microsoft Purview コンプライアンス ポータル。 したがって、DLP レポートのコマンドレットを使用するには、次の操作を行う必要があります。
  
1. [リモート PowerShell で Exchange Online に接続する](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. DLP レポート用のいずれかのコマンドレットを使用します。
    
      - [Get-DlpDetectionsReport](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [Get-DlpDetailReport](/powershell/module/exchange/get-dlpdetailreport)
