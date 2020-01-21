---
title: 機密ラベルを作成して発行する
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 組織のドキュメントやメールを分類し、保護するための機密ラベルを作成、構成、発行する手順です。
ms.openlocfilehash: 200b101b0083abbba90eaced9720db854ff02bbb
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233864"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>機密ラベルとそのポリシーを作成して構成する

[機密ラベル](sensitivity-labels.md)を作成して発行するには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)などラベル付けの管理センターに移動します。 Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターを使用することもできます。

まず、Office 用のアプリとサービスで使用する機密ラベルを作成し、構成します。 次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。 このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。

## <a name="create-and-configure-sensitivity-labels"></a>機密ラベルを作成して構成する

1. ラベル付けの管理センターで、**[分類]**  >  **[機密ラベル]** の順に移動します。

2. **[ラベル]** タブで、**[+ ラベルの作成]** を選択して、**[新しい機密ラベル]** ウィザードを起動します。

3. ラベル設定の指示に従います。
    
    ラベル設定の詳細については、「概要」の「[機密ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。

4. さらにラベルを作成するには、これらの手順を繰り返します。 ただし、サブ ラベルを作成する場合は、まず親ラベルを選択してから、**[その他のアクション]** の **[...]** を選択し、**[サブ ラベルの追加]** を選択ます。

5. 必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。 ラベルの順序を変更するには、**[その他のアクション]** の **[...]** を選択して、**[上へ移動]** または **[下へ移動]** を選択します。 詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。

既存のラベルを編集するには、目的のラベルを選択し、**[ラベルの編集]** を選択します。 これにより、**[機密ラベルの編集]** ウィザードが起動し、手順 3 のすべてのラベル設定を変更できます。 ラベル ポリシーを使用して既にラベルが発行されている場合は、追加の手順は必要ありませんが、変更がユーザーと場所にレプリケートされるまでに最大 24 時間かかります。

ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。 ラベルを発行するには、ラベルをラベル ポリシーに追加する必要があります。

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定

[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル設定を使用できます。

たとえば、*LocaleSettings* パラメーターを使用して、ラベル名とヒントに別の言語を指定できます。 

このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することもできます。 この詳細設定には、ラベルが適用されたときのラベルの色の設定やカスタム プロパティの適用が含まれます。 完全な一覧については、「[利用できるラベル ポリシーの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)」を参照してください。 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>ラベル ポリシーを作成して機密ラベルを発行する

1. ラベル付けの管理センターで、**[分類]**  >  **[機密ラベル]** の順に移動します。

2. **[ラベル ポリシー]** タブをクリックします。

3. **[ラベルの発行]** を選択し、**[ポリシーの作成] ウィザード**を起動します。

4. **[発行する機密ラベルの選択]** をクリックします。 アプリとサービスで使用するラベルを選択し、**[追加]** を選択します。

5. 選んだラベルを確認し、変更を加える場合は **[編集]** を選択します。 それ以外の場合は、**[次へ]** を選択します。

6. 指示に従ってポリシー設定を構成します。
    
    設定の詳細については、「概要」の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。

7. 異なるユーザーや場所に対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。 たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。

8. 複数のラベル ポリシーを作成すると、ユーザーまたは場所の競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。 ラベル ポリシーの順序を変更するには、**[その他のアクション]** の **[...]** を選択して、**[上へ移動]** または **[下へ移動]** を選択します。 詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。

ウィザードを完了すると、ラベル ポリシーが自動的に発行されます。 発行したポリシーは、簡単に編集して変更することができます。 特定の発行や再発行のアクションを選択する必要はありません。

既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、**[ポリシーの編集]** を選択します。 これにより、**[ポリシーの作成]** ウィザードが起動し、含めるラベルとラベルの設定を編集できます。 ウィザードを完了すると、選択したユーザーと場所に変更が自動的にレプリケートされます。 レプリケーションが完了するまでに最大 24 時間かかります。

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定

[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル ポリシー設定を使用できます。

このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することができます。 この詳細設定には、Outlook 用の異なる既定ラベルが含まれています。また、送信メールの警告、両端揃え、ブロックを行うポップアップ メッセージを Outlook に実装しています。 完全な一覧については、「[利用できるラベルの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。 

このコマンドレットを使用して、ラベル ポリシーへのラベルの追加や削除も可能です。


## <a name="next-steps"></a>次の手順

特定のシナリオで機密ラベルを構成して使用するには、次の記事を参照してください。

- [機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する](encryption-sensitivity-labels.md)

- [機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)

- [チーム、グループ、およびサイトで機密度ラベルを使用する](sensitivity-labels-teams-groups-sites.md)

- [SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)

ラベルがどのように使われているかを監視するには、「[ラベル分析によるラベル使用状況の表示](label-analytics.md)」を参照してください。