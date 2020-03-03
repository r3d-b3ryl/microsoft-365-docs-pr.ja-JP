---
title: Microsoft のセキュリティで保護されたスコアについて
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細情報の計算方法、およびセキュリティ管理者が期待できるセキュリティについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372005"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft のセキュリティで保護されたスコアについて

Microsoft のセキュリティスコアをより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。 スコアと可能な最大スコアが変わります。 ただし、これはセキュリティに関する姿勢の変化を意味するものではありません。

最近の変更については、「 [Microsoft のセキュリティで保護されたスコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。

## <a name="march-16th-2020"></a>2020年3月16日

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>信頼性の高い測定要件を満たしていない、またはセキュリティに関する有益な表現を提供していない改善アクションを削除する

マイクロソフトのセキュリティスコアが意味があり、すべての改善アクションが測定可能で信頼性を備えていることを確認するために、次の改善アクションを削除しています。

- OneDrive for business でユーザーのドキュメントを保存する
- Office 365 の ATP の安全な添付ファイルポリシーを設定する
- Office 365 の安全なリンクを設定して Url を確認する
- メールボックスの委任を許可しない
- サイトおよびドキュメントの匿名ゲスト共有リンクを許可する
- Cloud App Security コンソールを有効にする
- 外部共有リンクの有効期限を構成する

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Azure AD 向上アクションのセキュリティの既定のサポート

Microsoft Secure Score は、強化された操作を更新して[AZURE AD のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートします。これにより、一般的な攻撃のために事前に構成されたセキュリティ設定を使用して組織を保護することが容易になります。

次の改善アクションに影響を与えます。

- すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする
- 管理役割に MFA を必要とする
- 従来の認証をブロックするポリシーを有効にする
