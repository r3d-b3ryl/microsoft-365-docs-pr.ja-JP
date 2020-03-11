---
title: Microsoft セキュア スコアの新機能
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、詳細をどのように計算するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372005"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft セキュア スコアの新機能

お客様により優れたセキュリティ体制を提供し、使いやすさを向上させるために、Microsoft セキュア スコアは近日中に変化が加えられます。 お客様のスコアと最大可能スコアが新しくなります。 ただし、これによりセキュリティ体制が変わるわけではありません。

最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。

## <a name="march-16th-2020"></a>2020 年 3 月 16 日

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>改善アクションのうち、信頼できる測定としての条件を満たさないもの、またはセキュリティ体制の形として有用でないものは、削除しています。

Microsoft セキュリティ スコアが有意義であり、すべての改善アクションが測定可能かつ信頼性の高いものになるよう、次の改善アクションについては削除します。

- OneDrive for Business でユーザー ドキュメントを保存する
- Office 365 ATP の安全な添付ファイルに関するポリシーを設定する
- Office 365 の安全なリンクをセットアップして URL を確認する
- メールボックスの委任を許可しない
- サイトとドキュメントの匿名ゲストの共有リンクを許可する
- Cloud App Security コンソールを有効にする
- 外部共有リンクの有効期限を構成する

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Azure AD の改善アクションに関するセキュリティの既定群をサポートする

Microsoft セキュア スコアは、[Azure AD のセキュリティの既定群](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションを更新します。これにより、構成済みのセキュリティ設定を使用して、一般的な攻撃から組織を保護することが簡単にできるようになります。

これは、次の改善アクションに影響します。

- 安全なアクセスのため、すべてのユーザーが多要素認証を行えるようにする
- 管理者の役割に MFA を要求する
- レガシ認証をブロックするポリシーを有効にする
