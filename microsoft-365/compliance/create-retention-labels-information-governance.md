---
title: アイテム保持ポリシーの例外の保持ラベルを作成する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 必要なものを保持し、不要なものを削除できるように、情報ガバナンスのアイテム保持ポリシーに対する例外の保持ラベルを作成する手順。
ms.openlocfilehash: 699df2a62204115c60271a5d5aa70613db48c7d5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327267"
---
# <a name="create-retention-labels-for-exceptions-to-your-retention-policies"></a>アイテム保持ポリシーの例外の保持ラベルを作成する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

必要なものを保持し、不要なものを削除するためのガバナンス情報戦略の一環として、アイテム保持ポリシーの例外を必要とするアイテムの保持ラベルをいくつか作成することが必要になる場合があります。 

アイテム保持ポリシーはコンテナー レベルのすべてのアイテム (SharePoint サイト、ユーザー メールボックスなど) に自動的に適用されますが、保持ラベルは、SharePoint ドキュメントやメール メッセージなどの個々のアイテムに適用されます。

特定の SharePoint、OneDrive、または Exchange アイテムのアイテム保持ポリシーを補完する保持ラベルを使用する前に、[保持の原則](retention.md#the-principles-of-retention-or-what-takes-precedence)を理解していることを確認してください。 通常、適用されたアイテム保持ポリシーよりも長く特定のアイテムを保持するために保持ラベルを使用しますが、保持期間の終了時に自動削除をオーバーライドしたり、別の削除期間を適用したりするために使用することもできます。

一般的な例として、SharePoint サイトのコンテンツの大部分は 3 年間保持する必要があり、これはアイテム保持ポリシーでカバーされます。 ただし、7 年間保持する必要がある契約ドキュメントがいくつかあります。 これらの例外は、保持ラベルを使用して対処できます。 アイテム保持ポリシーをすべての SharePoint サイトに割り当てた後、保持ラベルを契約ドキュメントに適用します。 すべての SharePoint アイテムは 3 年間保持され、契約ドキュメントのみが 7 年間保持されます。

保持ラベルをアイテム保持ポリシーの例外として使用する方法の詳細については、「[アイテム保持ポリシーと保持ラベルの組み合わせ](retention.md#combining-retention-policies-and-retention-labels)」を参照してください。

保持ラベルでは、アイテム保持ポリシーよりも多くの機能もサポートされます。 詳細については、「[アイテム保持ポリシーと保持ラベルの機能](retention.md#compare-capabilities-for-retention-policies-and-retention-labels)」を参照してください。

次の情報は、情報ガバナンス戦略の一部としてアイテム保持ポリシーを補完する保持ラベルを作成するのに役立ちます。

> [!NOTE]
> ビジネス、法務、または規制上の記録保持要件に関わる貴重なアイテムのライフサイクル管理に保持ラベルを使用する必要がある場合は、**情報ガバナンス** ではなく、**レコード管理** ソリューションから保持ラベルを作成します。 たとえば、イベント ベースの保持または廃棄レビューを使用するとします。 手順については、「[ファイル計画を使用して保持ラベルを作成および管理する](file-plan-manager.md)」を参照してください。

## <a name="before-you-begin"></a>はじめに

組織のグローバル管理者には、保持ラベルとそれらのポリシーを作成および編集できる完全な権限があります。 グローバル管理者としてサインインしていない場合は、「[アイテム保持ポリシーと保持ラベルへのアクセス許可](get-started-with-information-governance.md#permissions-for-retention-policies-and-retention-labels)」を参照してください。

## <a name="how-to-create-retention-labels-for-information-governance"></a>情報ガバナンスの保持ラベルを作成する方法

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、**[ソリューション]** > **[情報ガバナンス]** > **[ラベル]** タブ > **[ラベルの作成]** の順に移動します
    
    **情報ガバナンス** ソリューションがすぐに表示されない場合 最初に [**すべて表示**] を選択します。 

2. メッセージに従って保持ラベルを作成します。 ラベルを保存すると変更できなくなるため、ラベルに選択する名前に注意してください。
    
    保持設定の詳細については、「[コンテンツを保持および削除するための設定](retention-settings.md#settings-for-retaining-and-deleting-content)」を参照してください。

3. ラベルを作成し、ラベルの公開、ラベルの自動適用、または単にラベルを保存するオプションが表示されたら、[**今すぐラベルを保存する**] を選択し、[**完了**] を選択します。

4. これらの手順を繰り返して、異なる保持設定に必要な保持ラベルを作成します。

既存のラベルを編集するには、そのラベルを選択してから **[ラベルの編集]** オプションを選択し、ラベルの説明や有効な設定を変更するための [保持ラベルの編集] 構成を開始します。

ラベルやポリシーを作成して保存すると、ほとんどの設定は変更できななくなります。これには次のものが含まれます。
- 保持ラベル名および保持期間を除く保持設定。 ただし、アイテムにラベルが付けられた時期に基づいて保持期間が設定されている場合、保持期間を変更することはできません。

## <a name="next-steps"></a>次の手順

保持ラベルを作成したので、ラベルを発行するか、自動的に適用することで、アイテムに追加する準備ができました。
- [アイテム保持ラベルを発行してアプリに適用する](create-apply-retention-labels.md)
- [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)