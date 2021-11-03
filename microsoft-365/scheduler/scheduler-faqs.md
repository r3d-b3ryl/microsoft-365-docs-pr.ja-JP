---
title: スケジューラー Microsoft 365 FAQ
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: スケジューラー Microsoft 365 FAQ
ms.openlocfilehash: 2392c48de3d80cf41d179eb053c46967626b5159
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60673302"
---
# <a name="scheduler-for-microsoft-365-faq"></a>スケジューラー Microsoft 365 FAQ

**質問:** Scheduler は、Cortana *Cortana、* 毎日のブリーフィンWindows、マイ メールの再生などの他の機能とどのように *統合しますか*。</br>
Scheduler は、他の機能と独立したサービスCortanaです。 その他Cortana機能はテナント レベルで無効にできます。また、スケジューラは引き続き電子メール アドレスを使用 cortana@yourdomain.com できます。 現時点では、ユーザーは電子メールを介してスケジューラーとのみ対話できます。

**質問:** この機能は、ユーザーのOutlook? 他の電子メール製品はサポートされていますか?</br>
上記の 3 つの要件以外のライセンスを持っている限り、ユーザーは任意の cortana@yourdomain.com クライアントから電子メールを送信できます。

**質問:** 連絡先は、連絡先と GAL または他の会社Outlook連絡先リストに含めできますか?</br>
会議の出席者には、会社の内部または外部に電子メール アドレスを持つユーザーを指定できます。 残念ながら、Scheduler は、今日の GAL で名前を参照して、名前を電子メール アドレス/エイリアスに自動的に変換することはできません。

**質問:** インストールされているバージョンの (オンプレミス) バージョンのスケジューラを使用Outlook?</br>
スケジューラには、Exchange Onlineが必要です。 (On-prem) Exchange Serverでは動作しません。 任意の電子メール クライアント、Outlook、OWA、iOS、android、gmail などと連携します。

**質問:** バックグラウンドOutlook開く必要がありますか?</br>
Outlookで開く必要はない。 必要なのは、メールを送信Cortana、そのメールを使用して作業の大部分を実行する必要があります。

## <a name="frequently-asked-trust-and-privacy-questions"></a>よく寄せられる信頼とプライバシーに関する質問

**質問:** スケジューラの動作方法</br>
スケジューラは、人間のアシスタントで拡張されたスケジューリング インテリジェンス (AI) を使用します。 AI モデルが、Cortana との自然なコミュニケーション言語でサポートを必要とする場合、会議出席依頼は確認と完了のために人間にエスカレートします。

**質問:** Who要求を確認する人はいますか? </br>
スケジューラ アシスタントは、Microsoft Supplier Security and Privacy Assurance (SSPA) の認定を受けた個人および機密性の高い情報です。

**質問:** SSPA アシスタントは何を表示できますか?</br>
スケジューラと SSPA アシスタントは、ユーザーにアドレス指定されたメールを表示Cortana。 スレッド化された電子メール交換では、Cortana の電子メール アドレスを含む電子メールだけが処理され、Cortana が追加される前のスレッド内の以前のメールは処理されません。

**質問:** 顧客データはスケジューラのデータ 管理に保持Flow? </br>
スケジューラは、テナント境界内のすべての顧客コンテンツを格納し、GDPR ガイドライン、Microsoft 365 Trust & プライバシー ポリシー、およびテナントの電子メール ポリシーに従ってデータを保持します。

**質問:** スケジューラーは、内部出席者の空き時間情報を処理する方法を説明します。 </br>
スケジューラの自動化では *、findMeetingTimes* サービスを使用して、出席者と開催者が相互に利用できる時間を特定します。 このサービスは、Outlookフォームの *[* 推奨された時間] などの他のOutlook機能します。 空き時間情報は、空き時間情報ブロックとして明示的に使用されません。

**質問:** Scheduler GDPR は準拠していますか? </br>
はい。

**質問:** WhoメールボックスにアクセスCortanaできますか? </br>
スケジューラーは、テナントのメールボックスに送信される会議出席依頼と関連Cortanaします。 Microsoft は、テナント管理者の要求に応じてロックボックスの承認をCortanaメールボックスへのその他のアクセス権を持つ必要があります。

**質問:** 顧客データは AI モデルのトレーニングに使用されますか?</br>
データ トレーニング セットに使用Microsoft 365スケジューラの顧客コンテンツは使用できません。 すべての顧客コンテンツは、顧客テナントに存在します。

**質問:** スケジューラは暗号化されたメールを処理しますか?</br>
いいえ、暗号化されたメールはスケジューラ ワークフローによって拒否されます。
