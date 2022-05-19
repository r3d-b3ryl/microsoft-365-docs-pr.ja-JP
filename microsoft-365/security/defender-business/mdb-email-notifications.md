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
ms.collection: M365-security-compliance
ms.openlocfilehash: 7dc6c65221211367e080fac46506f209d17f88ff
ms.sourcegitcommit: 60970cf8a2cb451011c423d797dfb77925394f89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2022
ms.locfileid: "65587448"
---
# <a name="set-up-email-notifications"></a>電子メール通知を設定する

セキュリティ チームの電子メール通知を設定できます。 その後、アラートが生成されるか、新しい脆弱性が検出されると、セキュリティ チームのユーザーに自動的に通知されます。 

## <a name="what-to-do"></a>操作

1. [電子メール通知の種類について説明します](#types-of-email-notifications)。
2. [電子メール通知の設定を表示および編集します](#view-and-edit-email-notifications)。
3. [次の手順に進みます](#next-steps)。


>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="types-of-email-notifications"></a>電子メール通知の種類

電子メール通知を設定するときは、次の表に示すように、2 つの種類から選択できます。

| 通知の種類  | 説明  |
|---------|---------|
| 脆弱 性  | 新しい悪用や脆弱性イベントが検出されるたびに、受信者は電子メールを受け取ります。 |
| アラート&脆弱性  | デバイスで脅威が検出されたためにアラートが生成された場合、または新しい悪用や脆弱性イベントが検出された場合、受信者は電子メールを受信します。 |

> [!TIP]
> **セキュリティ チームが新しいアラートや脆弱性について知ることができる唯一の方法は、電子メール通知ではありません**。
> 
> 電子メール通知は、セキュリティ チームにリアルタイムで情報を提供するのに役立つ便利な方法です。 しかし、他にも存在します。 たとえば、セキュリティ チームが Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) にサインインするたびに、新しい脅威、アラート、および脆弱性を強調するカードが表示されます。 Defender for Business は、セキュリティ チームがサインインするとすぐに気になる重要な情報を強調表示するように設計されています。
> 
> セキュリティ チームは、ナビゲーション ウィンドウで **[インシデント** ] を選択して情報を表示することもできます。 詳細については、「[Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)」を参照してください。

## <a name="view-and-edit-email-notifications"></a>電子メール通知を表示および編集する

会社の電子メール通知設定を表示または編集するには、次の手順に従います。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで[**設定**]、[エンドポイント] の順 **に** 選択します。 次に、[ **全般**] で [ **電子メール通知**] を選択します。 

3. **[アラート**] タブと [脆弱性] タブの情報 **を** 確認します。

   - [アラート] タブに項目が表示されない場合は、 **アラート** が生成されたときに通知を受け取るルールを作成できます。 このタスクのヘルプについては、「 [アラート通知のルールを作成する」を](../defender-endpoint/configure-email-notifications.md)参照してください。

   - [ **脆弱性** ] タブに項目が表示されない場合は、新しい脆弱性が検出されるたびに通知を受け取るルールを作成できます。 このタスクのヘルプについては、「 [脆弱性イベントのルールを作成する」を](../defender-endpoint/configure-vulnerability-email-notifications.md)参照してください。

   - ルールが作成されている場合は、ルールを選択して編集します。 ルールを削除することもできます。 

> [!IMPORTANT]
> Defender for Business で電子メール通知を設定するときは、通知ルールを特定のユーザーに割り当てる必要があります。 Defender for Business では、 [Defender for Endpoint のようなロールベースのアクセス制御は](../defender-endpoint/rbac.md)使用されません。 また、Defender for Business のデバイス グループに電子メール通知を適用することはできません。 

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 4: デバイスをMicrosoft Defender for Businessにオンボードする](mdb-onboard-devices.md)
