---
title: 'Scheduler for Microsoft 365 の FAQ '
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: 'Scheduler for Microsoft 365 の FAQ '
ms.openlocfilehash: 2392c48de3d80cf41d179eb053c46967626b5159
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703327"
---
# <a name="scheduler-for-microsoft-365-faq"></a>Scheduler for Microsoft 365 の FAQ 

**質問：** Scheduler と他のCortana機能 (Windows、*毎日のブリーフィング メール*、*Play My Emails* *のCortana* など) をどのように統合しますか?</br>
Scheduler は、他のCortana機能から独立したサービスです。 その他のCortana機能はテナント レベルで無効にできます。また、cortana@yourdomain.com 電子メール アドレスを使用して Scheduler を有効にすることもできます。 現時点では、ユーザーは電子メールを介してのみ Scheduler を操作できます。

**質問：** これはOutlookでのみ機能しますか? その他のメール製品はサポートされていますか?</br>
上記の 3 つの要件以外のライセンスを持っている限り、ユーザーは任意のデバイス上の任意の電子メール クライアントから cortana@yourdomain.com を電子メールで送信できます。

**質問：** 連絡先は、Outlookおよび GAL またはその他の会社と同等の個人の連絡先リストに含めることができますか?</br>
会議の出席者は、社内外のメール アドレスを持つすべてのユーザーにすることができます。 残念ながら、Scheduler では、現在 GAL で検索することで、名前を電子メール アドレス/エイリアスに自動的に変換することはできません。

**質問：** インストールされているバージョン (オンプレミス) バージョンのOutlookで Scheduler を使用できますか?</br>
スケジューラにはExchange Onlineが必要です。 Exchange Server (On-prem) では動作しません。 任意の電子メール クライアント、Outlook Desktop、OWA、iOS、android、gmail などと連携します。

**質問：** Outlookバックグラウンドで開く必要がありますか?</br>
Outlookはバックグラウンドで開く必要はありません。 必要なのは、メールCortana送信し、それを利用して作業の大部分を行うことです。

## <a name="frequently-asked-trust-and-privacy-questions"></a>よく寄せられる信頼とプライバシーに関する質問

**質問：** Scheduler のしくみ</br>
Scheduler は、人間のアシスタントで拡張されたスケジュール インテリジェンス (AI) を使用します。 AI モデルがCortanaとの自然なコミュニケーション言語でサポートの必要性を生み出す場合、会議出席依頼はレビューと完了のために人にエスカレートします。

**質問:** エスカレートされた要求を確認する人間はWhoですか? </br>
スケジューラ アシスタントは、個人情報と機密性の高い情報に対して認定された Microsoft Supplier Security and Privacy Assurance (SSPA) です。

**質問：** SSPA アシスタントは何を表示できますか?</br>
スケジューラと SSPA アシスタントは、Cortana宛てメールを表示できます。 スレッド化された電子メール交換では、Cortanaのメール アドレスを含むメールのみが処理され、Cortanaが追加される前のスレッド内の以前のメールは処理されません。

**質問：** スケジューラのData Flowに顧客データは保持されますか? </br>
Scheduler は、すべての顧客コンテンツをテナント境界内に格納し、GDPR ガイドライン、Microsoft 365信頼&プライバシー ポリシー、テナント電子メール ポリシーに従ってデータを保持します。

**質問：** Scheduler は内部出席者の空き時間データをどのように処理しますか? </br>
Scheduler の自動化では *、findMeetingTimes サービスを* 使用して、出席者と開催者が相互に利用できる時間を特定します。 このサービスは、Outlook会議フォームの *推奨時間* などの他のOutlookエクスペリエンスを提供します。 空き時間の出席者情報は、空き時間ブロックとして明示的に使用されません。

**質問：** Scheduler GDPR は準拠していますか? </br>
はい。

**質問:** 誰がCortana メールボックスにアクセスできますか? </br>
Scheduler は、テナントのCortanaメールボックスに送信される会議出席依頼と関連する電子メールを処理します。 Microsoft は、テナント管理者の要求によるロックボックスの承認を除き、Cortana メールボックスに対するその他のアクセス権を持っていません。

**質問：** 顧客データは AI モデルのトレーニングに使用されますか?</br>
データ トレーニング セットにMicrosoft 365の Scheduler の顧客コンテンツを使用することはできません。 すべての顧客コンテンツは、顧客テナントに存在します。

**質問：** Scheduler は暗号化されたメールを処理しますか?</br>
いいえ。暗号化されたメールは Scheduler ワークフローによって拒否されます。
