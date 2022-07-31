---
title: メッセージの委任
author: samanro
ms.author: samanro
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: acolonna
description: '[退席] または [応答不可] の状態のユーザーが、別のユーザーを状態メッセージで代理人として明示的に設定する方法について説明します。'
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 190b1f8bfdcf06c124163d97ecf77465f66ad67c
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994801"
---
# <a name="message-delegation"></a>メッセージの委任

ユーザーは既に状態を [退席中] または [応答不可] に明示的に設定し、カスタム テキストを指定できます。 メッセージ委任機能は次のように機能します。

1. ユーザー@username、テキストステータス メッセージの一部で別のユーザーをメンションし、ユーザーに連絡するユーザーが利用不可の場合は、そのユーザーに連絡する代わりに、@username言及されたユーザーに連絡することを提案します。
2. 代理人として割り当てられたユーザーには、代理人として指名されたことが通知されます。
3. 最初のユーザーに問い合わせようとしているユーザーは、指定したデリゲートにマウス ポインターを合わせ、代わりに代理人に簡単にメッセージを送信できます。  

これはクライアントでユーザーが開始するプロセスであり、この機能を有効にするために管理関与する必要はありません。 

## <a name="delegation-use-scenario-in-healthcare"></a>Healthcare での委任の使用シナリオ

*代理人を設定しない使用例:*  Dr. Franco Piccio は、ラジオロジー部門でオンコールです。 彼は緊急の個人的な電話を受け、次の数時間離れる必要があります。 彼は、ラジオロジー部門の同僚の 1 人である Lena Ehrle 博士に、彼がいなくなった間にカバーするように依頼します。 彼は、ポケットベルで緊急のメッセージや ping を聞いている Ehrle 博士にポケットベルを非公式に渡し、現在の責任に加えて、Piccio 博士に代わってそれらに応答します。 チームの他のユーザーは、非公式の委任が行われることに気付かない可能性があり、患者のケアに混乱が生じます。

*代理人を設定する使用例:* Dr. Franco Piccio は、ラジオロジー部門でオンコールです。 彼は緊急の個人的な電話を受け、次の数時間離れる必要があります。 彼は、ラジオロジー部門の同僚の 1 人である Lena Ehrle 博士に、彼がいなくなった間にカバーするように依頼します。 "次の数時間は利用できません。 緊急時は@DrEhrleにお問い合わせください。  チームの他のユーザーは、委任が Piccio 博士と連絡を取ろうとしているときに発生したことを認識しているため、その間に Ehrle 博士に連絡する必要があります。 患者のケアに混乱がほとんどありません。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>共存モードが Teams クライアントのユーザー状態に与える影響

管理者は、状態ノートと委任メンションの動作が、ユーザーの共存モードに部分的に依存することを認識する必要があります。 このマトリックスは、次の可能性を示しています。

|Co-Existence モード | 期待される動作|
|---|---|
|TeamsOnly |ユーザーは Teams からのみメモを設定できます。 <br> ユーザーの Teams ノートは Teams & SfB に表示されます。 |
|アイランド | Teams に設定されたユーザーのメモは、Teams でのみ表示されます。 <br> SfB で設定されたユーザーのノートは SfB でのみ表示されます |
|SfB* モード | ユーザーは SfB からのみメモを設定できます。 <br> ユーザーの SfB ノートは、SfB & Teams に表示されます。  |
|||

ユーザーが TeamsOnly または Islands モードの場合にのみ、Teams でメモを設定できます。  

### <a name="displaying-notes-set-in-skype-for-business"></a>Skype for Businessでのノート セットの表示
  
ノートがSkype for Businessから設定されたことを視覚的に示す情報はありません。

Skype for Businessは、状態ノートに文字制限を適用しません。 Microsoft Teams では、Skype for Businessのノート セットの最初の 280 文字のみが表示されます。 ノートの末尾にある省略記号 (...) は、切り捨てを示します。
  
Skype for Businessノートの有効期限はサポートされていません。

ユーザーが TeamsOnly モードにアップグレードされている場合、Skype for Businessから Teams へのノートの移行はサポートされません。

## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](/microsoftteams/coexistence-chat-calls-presence)
