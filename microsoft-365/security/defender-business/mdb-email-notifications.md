---
title: セキュリティ チームの電子メール通知を設定する
description: Defender for Business のアラートと脆弱性についてセキュリティ チームに通知するように電子メール通知を設定します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: 58de1c63995521794fa368f64601221a3c9668ee
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67319891"
---
# <a name="set-up-email-notifications"></a>電子メール通知を設定する

セキュリティ チームの電子メール通知を設定できます。 その後、アラートが生成されるか、新しい脆弱性が検出されると、セキュリティ チームのユーザーに自動的に通知されます。 

## <a name="what-to-do"></a>操作

1. [メール通知の種類について学ぶ](#types-of-email-notifications)。
2. [メール通知設定の表示と編集](#view-and-edit-email-notifications)。
3. [次の手順に進みます](#next-steps)。

## <a name="types-of-email-notifications"></a>電子メール通知の種類

電子メール通知を設定するときは、次の表に示すように、2 つの種類から選択できます。

| 通知の種類  | 説明  |
|---------|---------|
| 脆弱 性  | 新しい悪用や脆弱性イベントが検出されるたびに、受信者は電子メールを受け取ります。 |
| アラート&脆弱性  | デバイスで脅威が検出されたためにアラートが生成された場合、または新しい悪用や脆弱性イベントが検出された場合、受信者は電子メールを受信します。 |

> [!TIP]
> **Email通知は、セキュリティ チームが新しいアラートや脆弱性について知る唯一の方法ではありません**。
> 
> Email通知は、セキュリティ チームにリアルタイムで情報を提供するのに役立つ便利な方法です。 しかし、他にも存在します。 たとえば、セキュリティ チームが Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) にサインインするたびに、新しい脅威、アラート、および脆弱性を強調するカードが表示されます。 Defender for Business は、セキュリティ チームがサインインするとすぐに気になる重要な情報を強調表示するように設計されています。
> 
> セキュリティ チームは、ナビゲーション ウィンドウで **[インシデント** ] を選択して情報を表示することもできます。 詳細については、「 [Defender for Business でのインシデントの表示と管理」を](mdb-view-manage-incidents.md)参照してください。

## <a name="view-and-edit-email-notifications"></a>電子メール通知を表示および編集する

会社の電子メール通知設定を表示または編集するには、次の手順に従います。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで [ **設定]** を選択し、[ **エンドポイント**] を選択します。 次に、[**全般**] で **[Email通知**] を選択します。 

3. **[アラート**] タブと [脆弱性] タブの情報 **を** 確認します。

   - [アラート] タブに項目が表示されない場合は、 **アラート** が生成されたときに通知を受け取るルールを作成できます。 このタスクのヘルプについては、「 [アラート通知のルールを作成する」を](../defender-endpoint/configure-email-notifications.md)参照してください。

   - [ **脆弱性** ] タブに項目が表示されない場合は、新しい脆弱性が検出されるたびに通知を受け取るルールを作成できます。 このタスクのヘルプについては、「 [脆弱性イベントのルールを作成する」を](../defender-endpoint/configure-vulnerability-email-notifications.md)参照してください。

   - ルールが作成されている場合は、ルールを選択して編集します。 ルールを削除することもできます。 

> [!IMPORTANT]
> Defender for Business で電子メール通知を設定するときは、通知ルールを特定のユーザーに割り当てる必要があります。 Defender for Business では、 [Defender for Endpoint のようなロールベースのアクセス制御は](../defender-endpoint/rbac.md)使用されません。 また、Defender for Business のデバイス グループに電子メール通知を適用することはできません。 

## <a name="next-steps"></a>次の手順

続行:

- [手順 4: Defender for Business にデバイスをオンボードする](mdb-onboard-devices.md)
