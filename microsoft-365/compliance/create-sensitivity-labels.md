---
title: 秘密度ラベルを作成して発行する
f1.keywords:
- NOCSH
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
description: 組織のドキュメントやメールを分類し、保護するための秘密度ラベルを作成、構成、発行する手順です。
ms.openlocfilehash: 73df1928a89218a419a9d774a7830ecad4aceb6d
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661863"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>秘密度ラベルとそのポリシーを作成して構成する

[秘密度ラベル](sensitivity-labels.md)を作成して発行するには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)などラベル付けの管理センターに移動します。 Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターを使用することもできます。

まず、Office 用のアプリとサービスで使用する秘密度ラベルを作成し、構成します。 次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。 このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>機密ラベルの作成と管理に必要なアクセス許可

機密ラベルを作成するコンプライアンス チームのメンバーは、Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターへのアクセス許可を持っている必要があります。 

既定では、テナント管理者はこれらの管理センターへのアクセス権を所有し、コンプライアンス責任者や他のユーザーにアクセス権を付与できます (テナント管理者が持つすべての権限を付与する必要はありません)。この委任された制限付き管理者アクセス許可については、これらのいずれかの管理センターの [**アクセス許可**] ページに移動して、[**コンプライアンス データ管理者**] 役割グループ、[**コンプライアンス管理者**] 役割グループ、または [**セキュリティ管理者**] 役割グループにユーザーを追加します。

手順については、「[ユーザーに Office 365 セキュリティ/センター コンプライアンス センターへのアクセスを許可する](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)」を参照してください。

これらのアクセス許可は、機密ラベルとそのラベル ポリシーの作成と構成を行う場合にのみ必要です。 アプリまたはサービスでラベルを適用するためには必要はありません。

## <a name="create-and-configure-sensitivity-labels"></a>秘密度ラベルを作成して構成する

1. ラベル付けの管理センターで、[秘密度ラベル] に移動します。
    
    - Microsoft 365 コンプライアンス センター: 
        - [**ソリューション**]  >  [**Information Protection**]
        
        このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。 
    
    - Microsoft 365 セキュリティ センター: 
        - [**分類**]  >  [**秘密度ラベル**]
    
    - Office 365 セキュリティ/コンプライアンス センター:
        - [**分類**]  >  [**秘密度ラベル**]

2. [**ラベル**] タブで、[**+ ラベルの作成**] を選択して、[**新しい秘密度ラベル**] ウィザードを起動します。

3. ラベル設定の指示に従います。
    
    ラベル設定の詳細については、「概要」の「[秘密度ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。

4. さらにラベルを作成するには、これらの手順を繰り返します。 ただし、サブ ラベルを作成する場合は、まず親ラベルを選択してから、[**その他のアクション**] の [**...**] を選択し、[**サブ ラベルの追加**] を選択ます。

5. 必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。 ラベルの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。 詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。

既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] を選択します。 これにより、[**秘密度ラベルの編集**] ウィザードが起動し、手順 3 のすべてのラベル設定を変更できます。 

> [!NOTE]
> ラベル ポリシーを使用して既に発行されているラベルを編集する場合、ウィザードを終了するときに、追加の手順は必要ありません。 たとえば、同じユーザーに変更を反映させるために、ラベルを新しいラベル ポリシーに追加する必要はありません。 ただし、変更をユーザーとサービスにレプリケートするには、最大で 24 時間かかります。

ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。 ラベルを発行するには、ラベルを[ラベル ポリシーに追加](#publish-sensitivity-labels-by-creating-a-label-policy)する必要があります。

> [!IMPORTANT]
> この [**ラベル**] タブで、新しいラベル ポリシーを作成する必要がある場合を除き、[**ラベルの発行**] タブ (またはラベル編集時の [**ラベルの発行**] ボタン) を選択しないでください。 複数のラベル ポリシーが必要になるのは、ユーザーが異なるラベルまたは異なるポリシー設定を必要とする場合だけです。 できるだけ少ないラベル ポリシーを目指します。組織用のラベル ポリシーを 1 つだけ用意することは珍しくありません。

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定

[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル設定を使用できます。

多国籍の展開では、ユーザーが自分のローカル言語でラベル名とヒントを表示できるように *LocaleSettings* パラメーターを使用します。 構成例については、次のセクションを参照してください。 

このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することもできます。 この詳細設定には、ラベルが適用されたときのラベルの色の設定やカスタム プロパティの適用が含まれます。 完全な一覧については、「[利用できるラベル ポリシーの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)」を参照してください。 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a>異なる言語向けに機密ラベルを構成する構成例

次の例では、ヒント用のプレースホルダー テキストが含まれる "Public" という名前のラベルの PowerShell 構成を示します。 この例では、ラベル名とヒントのテキストはフランス語、イタリア語、ドイツ語向けに構成されます。

この構成の結果、これらの表示言語を使用する Office アプリを所有するユーザーには、ラベル名とツールヒントが同じ言語で表示されるようになります。 同様に、ファイルへのラベル付けをエクスプローラーから行うために Azure Information Protection 統一ラベル付けクライアントがインストールされている場合、これらの言語バージョンの Windows を所有しているユーザーがラベル付けのために右クリック アクションを使用すると、ラベル名とツールヒントがローカル言語で表示されます。

サポートする必要がある言語については、Office の[言語識別子](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (言語タグとも呼ばれます) を使用して、ラベル名とツールヒントの独自の翻訳を指定します。

PowerShell でコマンドを実行する前に、最初に [Office 365 セキュリティ/コンプライアンス センターの PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)する必要があります。


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress)
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>ラベル ポリシーを作成して秘密度ラベルを発行する

1. ラベル付けの管理センターで、[秘密度ラベル] に移動します。
    
    - Microsoft 365 コンプライアンス センター: 
        - [**ソリューション**]  >  [**Information Protection**]
        
        このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。 
    
    - Microsoft 365 セキュリティ センター: 
        - [**分類**]  >  [**秘密度ラベル**]
    
    - Office 365 セキュリティ/コンプライアンス センター:
        - [**分類**]  >  [**秘密度ラベル**]

2. [**ラベル ポリシー**] タブを選択します。

3. [**ラベルの発行**] を選択し、[**ポリシーの作成] ウィザード**を起動します。

4. [**発行する秘密度ラベルの選択**] をクリックします。 アプリとサービスで使用するラベルを選択し、[**追加**] を選択します。

5. 選択したラベルを確認し、変更する場合は [**編集**] を選択します。 それ以外の場合は、[**次へ**] を選択します。

6. 指示に従ってポリシー設定を構成します。
    
    設定の詳細については、「概要」の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。

7. 異なるユーザーや場所に対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。 たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。

8. 複数のラベル ポリシーを作成すると、ユーザーまたは場所の競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。 ラベル ポリシーの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。 詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。

ウィザードを完了すると、ラベル ポリシーが自動的に発行されます。 発行したポリシーは、簡単に編集して変更することができます。 特定の発行や再発行のアクションを選択する必要はありません。

既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、[**ポリシーの編集**] を選択します。 これにより、[**ポリシーの作成**] ウィザードが起動し、含めるラベルとラベルの設定を編集できます。 ウィザードを完了すると、選択したユーザーとサービスに変更が自動的にレプリケートされます。

通常、Office アプリのラベルは数時間以内にユーザーに表示されます。 ただし、ラベル ポリシーおよびそれらに対する変更を最大 24 時間使用して、すべてのユーザとサービスにレプリケートされます。

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定

[Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) の [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) コマンドレットを使ってその他のラベル ポリシー設定を使用できます。

このコマンドレットを使用すると、Azure Information Protection の統合ラベル付けクライアントに対して[詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)を指定することができます。 この詳細設定には、Outlook 用の異なる既定ラベルが含まれています。また、送信メールの警告、両端揃え、ブロックを行うポップアップ メッセージを Outlook に実装しています。 完全な一覧については、「[利用できるラベルの詳細設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。 

このコマンドレットを使用して、ラベル ポリシーへのラベルの追加や削除も可能です。


## <a name="next-steps"></a>次の手順

特定のシナリオで秘密度ラベルを構成して使用するには、次の記事を参照してください。

- [機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する](encryption-sensitivity-labels.md)

- [機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)

- [チーム、グループ、およびサイトで機密度ラベルを使用する](sensitivity-labels-teams-groups-sites.md)

- [SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)

ラベルがどのように使われているかを監視するには、「[ラベル分析によるラベル使用状況の表示](label-analytics.md)」を参照してください。