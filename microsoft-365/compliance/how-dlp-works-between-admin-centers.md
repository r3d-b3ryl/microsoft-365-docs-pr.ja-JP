---
title: 管理センターでのセキュリティ &コンプライアンス センター& Exchange DLP の動作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: セキュリティ & コンプライアンス センターの DLP とメール フロー ルール (トランスポート ルール) が管理センターでどのように動作Exchangeします。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 90706b3dad55ff84d274656673f9a60dbd71e35f
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423685"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a>コンプライアンス センターと管理センターの間Microsoft 365 DLP の動作Exchange方法

このMicrosoft 365、2 つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。
  
- Microsoft 365 **コンプライアンス** センターでは、SharePoint、OneDrive、Exchange、Teams、および現在のエンドポイント デバイスのコンテンツを保護するために、単一の DLP ポリシーを作成できます。 ここで DLP ポリシーを作成することをお勧めします。 詳細については、「データ損失防止 [リファレンス」を参照してください](data-loss-prevention-policies.md)。
    
- 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchangeで</a>、DLP ポリシーを作成して、コンテンツの保護をサポートExchange。 このポリシーでは、Exchangeフロー ルール (トランスポート ルールとも呼ばれる) を使用できます。そのため、メールの処理に固有のオプションが追加されています。 詳細については、管理センターの[DLP をExchangeしてください](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。
    
これらの管理センターで作成された DLP ポリシーは、サイド バイ サイドで機能します。このトピックでは、方法について説明します。
  
![[セキュリティとコンプライアンス センター] および [管理センター Exchange DLP ページ。](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>セキュリティ コンプライアンス センターの DLP &管理センターの DLP およびメール フロー ルールExchangeする方法

セキュリティ & コンプライアンス センターで DLP ポリシーを作成すると、ポリシーに含まれるすべての場所にポリシーが展開されます。 ポリシーに Exchange Onlineが含まれる場合、ポリシーはそこに同期され、Exchange 管理センターで作成された DLP ポリシーとまったく<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">同じ方法で適用されます</a>。 
  
Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは引き続きセキュリティ & コンプライアンス センターで作成した電子メールのポリシーと並べて機能します。 ただし、管理センターで作成されたExchangeが優先されます。 すべてのExchangeフロー ルールが最初に処理され、次にセキュリティ ポリシー コンプライアンス センター& DLP ルールが処理されます。
  
これは、次の意味を持つ。
  
- メール フロー ルールによってブロックExchangeメッセージは、セキュリティ コンプライアンス センターで作成された DLP ルール&されません。

- DLP が DLP によってスキャンExchange前に、メール フロー ルールまたは他のフィルターによって検疫されるメッセージ。
    
- Exchange メール フロー ルールが、セキュリティ & コンプライアンス センターの DLP ポリシー (外部ユーザーの追加など) に一致する方法でメッセージを変更した場合、DLP ルールはこれを検出し、必要に応じてポリシーを適用します。
    
また、「処理Exchange停止」アクションを使用するメール フロー ルールは、セキュリティ & コンプライアンス センターでの DLP ルールの処理には影響を与え、引き続き処理されます。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>コンプライアンス センターとセキュリティ &管理センターのExchangeヒント

ポリシー ヒントは<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">、Exchange</a>管理センターで作成された DLP ポリシーとメール フロー ルール、またはセキュリティ & コンプライアンス センターで作成された DLP ポリシーを使用して動作できますが、両方を使用することはできません。 これは、これらのポリシーは異なる場所に保存されますが、ポリシー ヒントは 1 つの場所からのみ描画できるためです。
  
Exchange 管理センターでポリシー ヒントを構成した場合、セキュリティ & コンプライアンス センターで構成したポリシー ヒントは、Exchange 管理センターでヒントをオフにするまで、Outlook on the web および Outlook 2013 以降のユーザーには表示されません。 これにより、セキュリティ Exchangeコンプライアンス センターに切り替えるまで、現在のメール フロー ルールが&されます。
  
ポリシー ヒントは 1 つの場所からしか描画されませんが、セキュリティ & コンプライアンス センターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されます。
