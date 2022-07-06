---
title: セキュリティ & コンプライアンス センター& Exchange 管理センターでの DLP のしくみ
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
description: セキュリティ & コンプライアンス センターの DLP が Exchange 管理センターの DLP およびメール フロー ルール (トランスポート ルール) と連携する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: fa77bf84ff8ef2b4f194f45b9a29b49f6b662a70
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66641408"
---
# <a name="how-dlp-works-between-the-compliance-center-and-exchange-admin-center"></a>コンプライアンス センターと Exchange 管理センターの間での DLP のしくみ

Microsoft Purview では、2 つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。
  
- **Microsoft Purview コンプライアンス ポータル** では、SharePoint、OneDrive、Exchange、Teams、および現在のエンドポイント デバイスのコンテンツを保護するために役立つ単一の DLP ポリシーを作成できます。 ここで DLP ポリシーを作成することをお勧めします。 詳細については、「 [データ損失防止のリファレンス」を参照してください](data-loss-prevention-policies.md)。
    
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>では、Exchange でのみコンテンツを保護するために役立つ DLP ポリシーを作成できます。 このポリシーでは、Exchange メール フロー ルール (トランスポート ルールとも呼ばれます) を使用できるため、電子メールの処理に固有のオプションが増えます。 詳細については、 [Exchange 管理センターの DLP に関するドキュメントを参照してください](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。
    
これらの管理センターで作成された DLP ポリシーは、並べて機能します。この記事では、その方法について説明します。
 
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>セキュリティ & コンプライアンス センターの DLP が Exchange 管理センターの DLP およびメール フロー ルールとどのように連携するか

セキュリティ & コンプライアンス センターで DLP ポリシーを作成すると、ポリシーはポリシーに含まれるすべての場所に展開されます。 ポリシーにExchange Onlineが含まれている場合、ポリシーは <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>で作成された DLP ポリシーとまったく同じ方法で同期され、適用されます。 
  
Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは、セキュリティ & コンプライアンス センターで作成した電子メールのポリシーと共に引き続き機能します。 ただし、Exchange 管理センターで作成されたルールが優先されることに注意してください。 すべての Exchange メール フロー ルールが最初に処理され、次にセキュリティ & コンプライアンス センターの DLP ルールが処理されます。
  
ということです：
  
- Exchange メール フロー ルールによってブロックされたメッセージは、セキュリティ & コンプライアンス センターで作成された DLP ルールではスキャンされません。
- Exchange メール フロー ルールまたはその他のフィルターによって検疫されたメッセージは、DLP によってスキャンされません。 
- Exchange メール フロー ルールが、外部ユーザーの追加など、セキュリティ & コンプライアンス センターの DLP ポリシーと一致するようにメッセージを変更した場合、DLP ルールはそれを検出し、必要に応じてポリシーを適用します。
    
また、"処理の停止" アクションを使用する Exchange メール フロー ルールは、セキュリティ & コンプライアンス センターの DLP ルールの処理には影響しません。それでも処理されます。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>セキュリティ & コンプライアンス センターと Exchange 管理センターのポリシーに関するヒント

ポリシー ヒントは、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>で作成された DLP ポリシーとメール フロー ルール、またはセキュリティ & コンプライアンス センターで作成された DLP ポリシーで機能しますが、両方では機能しません。 これは、これらのポリシーは異なる場所に格納されますが、ポリシーヒントは 1 つの場所からのみ描画できるためです。
  
Exchange 管理センターでポリシー ヒントを構成した場合、セキュリティ & コンプライアンス センターで構成したポリシー ヒントは、Exchange 管理センターでヒントをオフにするまで、Outlook on the webおよび Outlook 2013 以降のユーザーには表示されません。 これにより、セキュリティ & コンプライアンス センターに切り替えるまで、現在の Exchange メール フロー ルールは引き続き機能します。
  
>[!Note]
>ポリシーヒントは 1 つの場所からしか描画できませんが、セキュリティ & コンプライアンス センターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されます。
