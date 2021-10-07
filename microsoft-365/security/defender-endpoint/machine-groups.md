---
title: Microsoft Defender for Endpoint でデバイス グループを作成および管理する
description: デバイス グループを作成し、グループに適用されるルールを確認して、デバイス グループに自動修復レベルを設定する
keywords: デバイス グループ、グループ、修復、レベル、ルール、aad グループ、役割、割り当て、ランク
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9576470b029ac97660868341c46ecda82662b36
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152023"
---
# <a name="create-and-manage-device-groups"></a>デバイス グループの作成と管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- Azure Active Directory
- Office 365

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

エンタープライズ シナリオでは、通常、セキュリティ操作チームには一連のデバイスが割り当てられます。 これらのデバイスは、ドメイン、コンピューター名、指定されたタグなどの一連の属性に基づいてグループ化されます。

Microsoft Defender for Endpoint では、デバイス グループを作成し、次の場合に使用できます。

- RBAC ロールが割り当てられている特定の Azure ADグループへのアクセス [を制限する](rbac.md)
- デバイスの異なるセットに対して異なる自動修復設定を構成する
- 自動調査中に適用する特定の修復レベルを割り当てる
- 調査では、グループ フィルターを使用 **して** 、[デバイス] リストを特定のデバイス グループに **フィルター処理** します。

役割ベースのアクセス (RBAC) のコンテキストでデバイス グループを作成して、デバイス グループをユーザー グループに割り当て、特定のアクションを実行したり情報を表示したりできるユーザーを制御できます。 詳細については、「役割ベースのアクセス [制御を使用してポータル アクセスを管理する」を参照してください](rbac.md)。

> [!TIP]
> RBAC アプリケーションの包括的な外観については、「SOC は RBAC でフラット [に実行されていますか」を参照してください](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)。

デバイス グループの作成プロセスの一環として、次の手順を実行します。

- そのグループの自動修復レベルを設定します。 修復レベルの詳細については、「自動化された調査を使用して脅威を調査および修復する」 [を参照してください](automated-investigations.md)。
- デバイス名、ドメイン、タグ、および OS プラットフォームに基づいてグループに属するデバイス グループを決定する一致ルールを指定します。 デバイスが他のグループと一致する場合は、最もランクの高いデバイス グループにのみ追加されます。
- デバイス グループにADする必要がある Azure ユーザー グループを選択します。
- 作成後、他のグループを基準にデバイス グループをランク付けします。

> [!NOTE]
> Azure グループを割り当てない場合は、すべてのユーザーがデバイス グループADアクセスできます。

## <a name="create-a-device-group"></a>デバイス グループの作成

1. ナビゲーション ウィンドウで、[エンドポイントのアクセス許可 **設定** \>  \> **グループ]** \> **を選択します**。

2. [デバイス **グループの追加] をクリックします**。

3. グループ名とオートメーション設定を入力し、グループに属するデバイスを決定する一致ルールを指定します。 「 [自動調査の開始方法」を参照してください](automated-investigations.md#how-the-automated-investigation-starts)。

    > [!TIP]
    > 組織単位でデバイスをグループ化する場合は、グループ所属のレジストリ キーを構成できます。 デバイスタグ付けの詳細については、「デバイス タグの作成と [管理」を参照してください](machine-tags.md)。

4. このルールに一致する複数のデバイスをプレビューします。 ルールに満足している場合は、[ユーザー アクセス] **タブをクリック** します。

5. 作成したデバイス グループにアクセスできるユーザー グループを割り当てる。

    > [!NOTE]
    > RBAC ロールに割り当てられているユーザー AD Azure へのアクセスのみを許可できます。

6. [閉じる] をクリックします。 構成の変更が適用されます。

## <a name="manage-device-groups"></a>デバイス グループの管理

デバイス グループのランクを昇格または降格して、一致中に優先度を高くまたは低くすることができます。 デバイスが複数のグループに一致すると、そのデバイスは最もランク付けされたグループにのみ追加されます。 グループを編集および削除することもできます。

> [!WARNING]
> デバイス グループを削除すると、電子メール通知ルールに影響を与える可能性があります。 電子メール通知ルールの下でデバイス グループが構成されている場合は、そのルールから削除されます。 デバイス グループが電子メール通知用に構成されている唯一のグループである場合、その電子メール通知ルールはデバイス グループと共に削除されます。

既定では、デバイス グループには、ポータル アクセス権を持つすべてのユーザーがアクセスできます。 Azure ユーザー グループをデバイス グループに割り当AD既定の動作を変更できます。

グループに一致しないデバイスは、グループ化されていないデバイス (既定) グループに追加されます。 このグループのランクを変更したり、削除したりすることはできません。 ただし、このグループの修復レベルを変更し、このグループにアクセスできる Azure ADグループを定義できます。

> [!NOTE]
> デバイス グループ構成に変更を適用するには、数分かかる場合があります。

### <a name="add-device-group-definitions"></a>デバイス グループ定義の追加

デバイス グループ定義には、条件ごとに複数の値を含めすることもできます。 複数のタグ、デバイス名、ドメインを 1 つのデバイス グループの定義に設定できます。

1. 新しいデバイス グループを作成し、[デバイス] タブ **を選択** します。
2. 条件の 1 つの最初の値を追加します。
3. 同 `+` じプロパティの種類の行を追加する場合に選択します。

> [!TIP]
> 同じ条件タイプの行の間に 'OR' 演算子を使用します。これにより、プロパティごとに複数の値を使用できます。
>
> プロパティの種類 (タグ、デバイス名、ドメイン) ごとに最大 10 行 (値) を追加できます。

デバイス グループ定義へのリンクの詳細については[、「Device groups - Microsoft 365」を参照してください](https://sip.security.microsoft.com/homepage)。

## <a name="related-topics"></a>関連トピック

- [役割ベースのアクセス制御を使用したポータル アクセスの管理](rbac.md)
- [デバイス タグの作成と管理](machine-tags.md)
- [API を使用してテナント デバイス グループのリストGraphする](/graph/api/device-list-memberof)
