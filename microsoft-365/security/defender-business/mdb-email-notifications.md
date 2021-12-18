---
title: セキュリティ チームの電子メール通知を設定する
description: Microsoft Defender for Business を使用してアラートと脆弱性についてユーザーに通知する電子メール通知を設定する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.openlocfilehash: 5ccad3a8765c18e1768f8245d90b255d50ee5182
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507370"
---
# <a name="set-up-email-notifications"></a>電子メール通知を設定する

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 


セキュリティ チームの電子メール通知を設定できます。 その後、アラートが生成されると、または新しい脆弱性が検出されると、セキュリティ チームのユーザーに自動的に通知されます。 

## <a name="what-to-do"></a>操作

1. [電子メール通知の種類について説明します](#types-of-email-notifications)。

2. [電子メール通知の設定を表示および編集します](#view-and-edit-email-notifications)。

3. [次の手順に進みます](#next-steps)。


## <a name="types-of-email-notifications"></a>電子メール通知の種類

電子メール通知を設定する場合は、次の表で説明するように、2 つの種類から選択できます。 <br/><br/>

| 通知の種類  | 説明  |
|---------|---------|
| 脆弱性  | 新しい悪用や脆弱性イベントが検出されると、受信者は電子メールを受信します。 |
| 脆弱性&警告  | デバイスで脅威が検出されたため、または新しい悪用や脆弱性イベントが検出された場合、受信者は電子メールを受信します。 |

> [!TIP]
> **セキュリティ チームが新しいアラートや** 脆弱性について知る唯一の方法は、電子メール通知ではありません。
> 
> メール通知は、セキュリティ チームにリアルタイムで情報を提供するのに役立つ便利な方法です。 しかし、他の人がいます! たとえば、セキュリティ チームが Microsoft 365 Defender ポータル ( ) にサインインすると、新しい脅威、アラート、および脆弱性が強調表示されたカード [https://security.microsoft.com](https://security.microsoft.com) が表示されます。 Defender for Business (プレビュー) は、セキュリティ チームがサインインするとすぐに気にしている重要な情報を強調表示するように設計されています。
> 
> セキュリティ チームは、ナビゲーション ウィンドウで **[インシデント]** を選択して情報を表示することもできます。 詳細については、「Microsoft Defender for Business でのインシデントの表示と管理 [(プレビュー)」を参照してください](mdb-view-manage-incidents.md)。

## <a name="view-and-edit-email-notifications"></a>メール通知の表示と編集

会社のメール通知設定を表示または編集するには、次の手順を実行します。

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション ウィンドウで、[エンドポイント] を選択 **設定** し、[エンドポイント]**を選択します**。 次に、[全般] **で、[** 電子メール通知 **] を選択します**。 

3. [アラートと脆弱性]**タブの****情報を確認** します。

   - [アラート] タブに一覧にアイテムが表示されない場合は、アラートが生成された場合にユーザーに通知するルールを作成できます。 このタスクのヘルプを表示するには、「 [アラート通知のルールを作成する」を参照してください](../defender-endpoint/configure-email-notifications.md)。

   - [脆弱性] タブに一覧にアイテムが表示されない場合は、新しい脆弱性が検出されるたびにユーザーに通知するルールを作成できます。 このタスクのヘルプについては、「脆弱性イベントの [ルールを作成する」を参照してください](../defender-endpoint/configure-vulnerability-email-notifications.md)。

   - ルールが作成されている場合は、ルールを選択して編集します。 ルールを削除できます。 

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 4: Microsoft Defender for Business にデバイスをオンボードする (プレビュー)](mdb-onboard-devices.md)
