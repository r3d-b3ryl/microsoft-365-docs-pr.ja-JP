---
title: セキュリティ & コンプライアンス センター& Exchange管理センターでの DLP のしくみ
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
description: セキュリティ & コンプライアンス センターの DLP が、Exchange管理センターの DLP およびメール フロー ルール (トランスポート ルール) と連携する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 0c5c6288ed9e3c1f536e7a221a270bad9663cf6b
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753410"
---
# <a name="how-dlp-works-between-the-compliance-center-and-exchange-admin-center"></a>コンプライアンス センターとExchange管理センターの間での DLP のしくみ

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purviewでは、2 つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。
  
- **Microsoft Purview コンプライアンス ポータル** では、SharePoint、OneDrive、Exchange、Teams、および現在のエンドポイント デバイスのコンテンツを保護するために役立つ単一の DLP ポリシーを作成できます。 ここで DLP ポリシーを作成することをお勧めします。 詳細については、「 [データ損失防止のリファレンス」を参照してください](data-loss-prevention-policies.md)。
    
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>では、Exchangeでのみコンテンツを保護するために役立つ DLP ポリシーを作成できます。 このポリシーではExchangeメール フロー ルール (トランスポート ルールとも呼ばれます) を使用できるため、電子メールの処理に固有のオプションが増えます。 詳細については、[Exchange管理センターの DLP に関する](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)Exchangeを参照してください。
    
これらの管理センターで作成された DLP ポリシーは、並べて機能します。この記事では、その方法について説明します。
  
![セキュリティとコンプライアンス センターと管理センター Exchange DLP ページ。](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>セキュリティ & コンプライアンス センターの DLP が、Exchange管理センターの DLP およびメール フロー ルールとどのように連携するか

セキュリティ & コンプライアンス センターで DLP ポリシーを作成すると、ポリシーはポリシーに含まれるすべての場所に展開されます。 ポリシーにExchange Onlineが含まれている場合、ポリシーはそこで同期され、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>で作成された DLP ポリシーとまったく同じ方法で適用されます。 
  
Exchange管理センターで DLP ポリシーを作成した場合、これらのポリシーは、セキュリティ & コンプライアンス センターで作成した電子メールのポリシーと共に引き続き機能します。 ただし、Exchange管理センターで作成されたルールが優先されることに注意してください。 Exchangeメール フロー ルールはすべて最初に処理され、次にセキュリティ & コンプライアンス センターの DLP ルールが処理されます。
  
ということです：
  
- Exchangeメール フロー ルールによってブロックされたメッセージは、セキュリティ & コンプライアンス センターで作成された DLP ルールによってスキャンされません。
- Exchangeメール フロー ルールまたはその他のフィルターによって検疫されたメッセージは、DLP によってスキャンされない前に実行されます。 
- Exchangeメール フロー ルールが、外部ユーザーの追加など、セキュリティ & コンプライアンス センター内の DLP ポリシーと一致するようにメッセージを変更した場合、DLP ルールはそれを検出し、必要に応じてポリシーを適用します。
    
また、"処理の停止" アクションを使用するExchangeメール フロー ルールは、セキュリティ & コンプライアンス センターの DLP ルールの処理には影響しません。それでも処理されます。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>セキュリティ & コンプライアンス センターとExchange管理センターのポリシーのヒント

ポリシー ヒントは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>で作成された DLP ポリシーとメール フロー ルール、またはセキュリティ & コンプライアンス センターで作成された DLP ポリシーを使用できますが、両方では機能しません。 これは、これらのポリシーは異なる場所に格納されますが、ポリシーヒントは 1 つの場所からのみ描画できるためです。
  
Exchange管理センターでポリシーヒントを構成した場合、セキュリティ & コンプライアンス センターで構成したポリシーヒントは、Exchange管理センターでヒントをオフにするまで、Outlook on the webおよびOutlook 2013 以降のユーザーには表示されません。 これにより、セキュリティ & コンプライアンス センターに切り替えるまで、現在のExchangeメール フロー ルールは引き続き機能します。
  
>[!Note]
>ポリシー ヒントは 1 つの場所からしか描画できませんが、セキュリティ & コンプライアンス センターとExchange管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されます。
