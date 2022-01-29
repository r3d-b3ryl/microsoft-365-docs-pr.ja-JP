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
ms.openlocfilehash: 6676840285ef94f2c3b4fd3e15bfc0b074833849
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242214"
---
# <a name="create-retention-labels-for-exceptions-to-your-retention-policies"></a>アイテム保持ポリシーの例外の保持ラベルを作成する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

必要なものを保持し、不要なものを削除するためのガバナンス情報戦略の一環として、アイテム保持ポリシーの例外を必要とするアイテムの保持ラベルをいくつか作成することが必要になる場合があります。 

アイテム保持ポリシーはコンテナー レベルのすべてのアイテム (SharePoint サイト、ユーザー メールボックスなど) に自動的に適用されますが、保持ラベルは、SharePoint ドキュメントやメール メッセージなどの個々のアイテムに適用されます。

[[保持の原則]](retention.md#the-principles-of-retention-or-what-takes-precedence) により、保持ラベルを使用して、同じ場所のアイテム保持ポリシーで指定した設定よりも早く保持または削除する必要がある特定の SharePoint、OneDrive、または Exchange アイテムのアイテム保持ポリシーを補完することができます。

たとえば、SharePoint サイトのコンテンツの大部分は 3 年間保持する必要があり、これはアイテム保持ポリシーでカバーされます。 ただし、7 年間保持する必要がある契約ドキュメントがいくつかあります。 これらの例外は、保持ラベルを使用して対処できます。 アイテム保持ポリシーをすべての SharePoint サイトに割り当てた後、保持ラベルを契約ドキュメントに適用します。 すべての SharePoint アイテムは 3 年間保持され、契約ドキュメントのみが 7 年間保持されます。

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