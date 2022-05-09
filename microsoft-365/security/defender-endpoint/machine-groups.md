---
title: Microsoft Defender for Endpointでデバイス グループを作成および管理する
description: デバイス グループを作成し、そのグループに適用されるルールを確認して自動修復レベルを設定する
keywords: デバイス グループ、グループ、修復、レベル、ルール、aad グループ、ロール、割り当て、ランク
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
ms.openlocfilehash: 951e49ddb7cb9ed0154fa70f66d54944a8aae066
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62214143"
---
# <a name="create-and-manage-device-groups"></a>デバイス グループの作成と管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Azure Active Directory
- Office 365
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

エンタープライズ シナリオでは、通常、セキュリティ運用チームに一連のデバイスが割り当てられます。 これらのデバイスは、ドメイン、コンピューター名、指定されたタグなどの一連の属性に基づいてグループ化されます。

Microsoft Defender for Endpointでは、デバイス グループを作成し、それらを使用して次のことができます。

- [RBAC ロールが割り当てられている](rbac.md)特定のAzure ADユーザー グループに関連するアラートとデータへのアクセスを制限する
- デバイスのセットごとに異なる自動修復設定を構成する
- 自動調査中に適用する特定の修復レベルを割り当てる
- 調査で、[**グループ**] フィルターを使用して、[**デバイス] の一覧** を特定のデバイス グループにフィルター処理します。

ロールベースのアクセス (RBAC) のコンテキストでデバイス グループを作成し、特定のアクションを実行できるユーザーを制御したり、デバイス グループをユーザー グループに割り当てて情報を表示したりできます。 詳細については、「 [ロールベースのアクセス制御を使用したポータル アクセスの管理](rbac.md)」を参照してください。

> [!TIP]
> RBAC アプリケーションの包括的な調査については、「RBAC を [使用して SOC がフラットに実行されているか](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)」を参照してください。

デバイス グループを作成するプロセスの一環として、次のことを行います。

- そのグループの自動修復レベルを設定します。 修復レベルの詳細については、「 [自動調査を使用して脅威を調査および修復する](automated-investigations.md)」を参照してください。
- デバイス名、ドメイン、タグ、および OS プラットフォームに基づいて、どのデバイス グループがグループに属するかを決定する照合ルールを指定します。 デバイスが他のグループにも一致する場合は、ランクが最も高いデバイス グループにのみ追加されます。
- デバイス グループにアクセスする必要があるAzure ADユーザー グループを選択します。
- 作成後に、デバイス グループを他のグループに対して相対的にランク付けします。

> [!NOTE]
> デバイス グループにAzure AD グループを割り当てない場合は、すべてのユーザーがデバイス グループにアクセスできます。

## <a name="create-a-device-group"></a>デバイス グループを作成する

1. ナビゲーション ウィンドウで、[**エンドポイント** \> **のアクセス許可** \> **デバイス グループ****設定**\>選択します。

2. [ **デバイス グループの追加]** をクリックします。

3. グループ名とオートメーション設定を入力し、グループに属するデバイスを決定する一致規則を指定します。 [自動調査の開始方法](automated-investigations.md#how-the-automated-investigation-starts)に関する説明を参照してください。

    > [!TIP]
    > デバイスのグループ化にタグ付けを使用する場合は、デバイス [タグの作成と管理](machine-tags.md)に関するページを参照してください。

4. この規則に一致する複数のデバイスをプレビューします。 ルールに問題がなければ、[ **ユーザー アクセス** ] タブをクリックします。

5. 作成したデバイス グループにアクセスできるユーザー グループを割り当てます。

    > [!NOTE]
    > RBAC ロールに割り当てられているAzure ADユーザー グループにのみアクセス権を付与できます。

6. [閉じる] をクリックします。 構成の変更が適用されます。

## <a name="manage-device-groups"></a>デバイス グループを管理する

デバイス グループのランクを昇格または降格して、照合中に優先度を高くまたは低くすることができます。 デバイスが複数のグループに一致すると、ランクが最も高いグループにのみ追加されます。 グループを編集および削除することもできます。

> [!WARNING]
> デバイス グループを削除すると、電子メール通知ルールに影響を与える可能性があります。 デバイス グループが電子メール通知ルールで構成されている場合は、そのルールから削除されます。 デバイス グループが電子メール通知用に構成されている唯一のグループである場合、その電子メール通知ルールはデバイス グループと共に削除されます。

既定では、デバイス グループにはポータル アクセス権を持つすべてのユーザーがアクセスできます。 既定の動作を変更するには、Azure AD ユーザー グループをデバイス グループに割り当てます。

グループに一致しないデバイスは、グループ化されていないデバイス (既定) グループに追加されます。 このグループのランクを変更したり、削除したりすることはできません。 ただし、このグループの修復レベルを変更し、このグループにアクセスできるAzure ADユーザー グループを定義できます。

> [!NOTE]
> デバイス グループの構成に変更を適用するには、最大で数分かかる場合があります。

### <a name="add-device-group-definitions"></a>デバイス グループ定義を追加する

デバイス グループ定義には、条件ごとに複数の値を含めることもできます。 複数のタグ、デバイス名、ドメインを 1 つのデバイス グループの定義に設定できます。

1. 新しいデバイス グループを作成し、[ **デバイス** ] タブを選択します。
2. 条件の 1 つに最初の値を追加します。
3. 同じプロパティの種類の行を追加する場合に選択 `+` します。

> [!TIP]
> 同じ条件型の行間で 'OR' 演算子を使用します。プロパティごとに複数の値を使用できます。
> タグ、デバイス名、ドメインなど、プロパティの種類ごとに最大 10 行 (値) を追加できます。

デバイス グループ定義へのリンクの詳細については、「[デバイス グループ - Microsoft 365 セキュリティ](https://sip.security.microsoft.com/homepage)」を参照してください。

## <a name="related-topics"></a>関連項目

- [ロールベースのアクセス制御を使用してポータル アクセスを管理する](rbac.md)
- [デバイス タグの作成と管理](machine-tags.md)
- [Graph APIを使用してテナント デバイス グループの一覧を取得する](/graph/api/device-list-memberof)
