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
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895443"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft セキュア スコアの新機能

お客様により優れたセキュリティ体制を提供し、使いやすさを向上させるために、Microsoft セキュア スコアは近日中に変化が加えられます。 お客様のスコアと最大可能スコアが新しくなります。 ただし、これによりセキュリティ体制が変わるわけではありません。

最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。

## <a name="april-21st-2020"></a>2020年4月21日

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>改善アクションのうち、信頼できる測定としての条件を満たさないもの、またはセキュリティ体制の形として有用でないものは、削除しています。

Microsoft セキュリティ スコアが有意義であり、すべての改善アクションが測定可能かつ信頼性の高いものになるよう、次の改善アクションについては削除します。

- 過去30日間に使用されていないアカウントの削除/ブロック
- グローバル管理者を5名未満で指定する
- ドキュメントへの IRM による保護の適用
- データ損失防止ポリシーの適用

### <a name="adding-additional-control-support-in-the-preview-version"></a>プレビューバージョンでのコントロールサポートの追加
- ユーザーが管理されていないアプリケーションに同意を付与できないようにする (現時点でリリースされているバージョンで利用可能)

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a>その他の Microsoft Cloud App Security 向上アクションのサポート
- ドメインコントローラーで印刷スプーラーサービスを無効にする
- セキュリティで保護されていない Kerberos 委任を変更して偽装を防止する
- Microsoft LAPS を使用してローカル管理者パスワードを保護および管理する
- 機密性の高いエンティティに対して、重要な移動パスリスクを軽減する
- 機密グループからの休止アカウントの削除
- セキュリティ保護のない SID 履歴属性をエンティティから削除する
- 安全でないアカウントの属性を解決する
- クリアテキストの資格情報の公開を停止する
- 従来のプロトコル通信を停止する
- 暗号使用率の低い停止

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Microsoft Defender ATP & 脆弱性管理 (TVM) のセキュリティに関する推奨事項のサポート
- リリースされた TVM で提供されるすべてのセキュリティの推奨事項は、Microsoft セキュリティスコアでも利用できるようになりました。
