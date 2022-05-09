---
title: Microsoft 365に Scheduler を使用する
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Microsoft 365に Scheduler を使用する。
ms.openlocfilehash: 19c8171e58706fde441ec2ffdd3c1c0d85a18b83
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211359"
---
# <a name="how-to-use-scheduler-for-microsoft-365"></a>Scheduler for Microsoft 365 の利用方法

Cortanaは自然言語を理解しています。 他の出席者とメールに cortana@yourdomain.com を含め、そこから引き継ぐCortana。 Cortanaは、会議の時間を確認する電子メール通知を送信し、進行状況を最新の状態に保ちます。

Scheduler を使用するには、Cortanaのメール アドレスを、会議相手に加えてメールに追加します。 Cortanaとその他の出席者へのメールで、自然言語を使用して会議をスケジュールするようにCortanaに指示します。  

## <a name="when-to-use-scheduler"></a>Scheduler を使用するタイミング

- **内部出席者との会議のスケジュール設定** Cortanaを使用して、5 人以下の出席者で会議をスケジュールします。 Cortanaは、Outlook予定表の他のユーザーに表示される空き時間情報に対して同じアクセス権を持ちます。 すべてのユーザーに適した時間を選択し、代わりに招待を送信します。 Cortanaは、スケジュールするすべての会議を自動的にTeams有効にします。 CC 行の参加者は、任意の出席者として招待を受け取ります。  

- **外部出席者との会議のスケジュール設定**  
Cortanaは、外部の招待者と通信して、会議に使用できる時間をネゴシエートします。 会議の時間を確認した後、Cortana出席者に招待を送信し、会議がスケジュールされたことを通知します。

## <a name="what-to-say-to-cortana"></a>Cortanaに何を言いますか?

Cortanaは自然言語を理解していますが、簡潔な言語をお勧めします。 

会議を要求するには、次のパターンを使用します。 [時間の長さ] 会議 [時間枠]をスケジュールします。  

- "来週 30 分間の会議をスケジュールする"  
- "1 月に会うために 1 時間を見つける" 
- "インド標準時に動作する 5 月の最初の週に 45 分を検索します。 

時間範囲を指定しない場合、Cortanaは翌営業日に会議を予約します。

## <a name="scheduling-across-multiple-time-zones"></a>複数のタイム ゾーン間でのスケジュール設定

複数のタイム ゾーン会議を要求するには、次のパターンを使用します。"[タイム ゾーン] で動作する [時間枠] で [時間の長さ] 会議をスケジュールします。 

Cortanaは、最初のメールでCortanaに要求した場合、別のタイム ゾーンの出席者に対応します。  

最初の要求をCortanaに送信した後、タイム ゾーンを変更することはできません。 一部のタイム ゾーンの省略形は同じで、最適な結果を得るには、完全なタイム ゾーン名を使用します。  

## <a name="organizer-guidance"></a>開催者のガイダンス

場合によっては、Cortanaが開催者としてガイダンスを求める場合があります。 Cortanaのメールの指示に従い、Cortanaメールの返信ボタンを使用して返信します。

## <a name="reschedule-or-cancel"></a>再スケジュールまたはキャンセル

スケジュールを変更または取り消す必要がある場合は、スレッド内のメールに返信し、会議に関するCortanaを入力し、"スケジュールの変更" または "キャンセル" を求めます。 

> [!NOTE]
> Cortana Scheduler によってスケジュールされていない会議のスケジュールを変更したり、キャンセルしたりすることはできません。  
