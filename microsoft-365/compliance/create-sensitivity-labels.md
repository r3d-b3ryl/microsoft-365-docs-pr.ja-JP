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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: 'すべての Microsoft Information Protection ソリューションの要件: 組織のデータを分類し、保護するための秘密度ラベルを作成、構成、発行します。'
ms.openlocfilehash: 94ef0959c7e4de78080c54487ba017e1f75329ff
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2021
ms.locfileid: "61072375"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>秘密度ラベルとそのポリシーを作成して構成する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

すべての Microsoft Information Protection ソリューション (MIP と略されることもあります) は、[秘密度ラベル](sensitivity-labels.md)を使用して実装されます。 それらのラベルを作成して発行するには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター</a>に移動します。 または以前のポータルである Office 365 セキュリティ/コンプライアンス センターを使用することもできます。

まず、アプリやその他のサービスで使用する秘密度ラベルを作成し、構成します。 たとえば、ユーザーに表示して Office アプリから適用するラベルです。 

次に、構成するラベルとポリシー設定を含む 1 つ以上のラベル ポリシーを作成します。 このラベル ポリシーで、選択したユーザーと場所のラベルと設定を発行します。

## <a name="before-you-begin"></a>はじめに

組織のグローバル管理者には、秘密度ラベルのすべての側面を作成および管理するための完全な権限があります。 グローバル管理者としてサインインしていない場合は、「[機密ラベルの作成と管理に必要なアクセス許可](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)」を参照してください。

## <a name="create-and-configure-sensitivity-labels"></a>秘密度ラベルを作成して構成する

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)から、**[ソリューション]** > **[Information Protection]** を選択します。
    
    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。

2. [**ラベル**] ページで、[**+ ラベルの作成**] を選択して、[新しい秘密度ラベル] 構成を起動します。 

    たとえば、Microsoft 365 コンプライアンス センターでは、次のようになります。

    ![秘密度ラベルを作成する。](../media/create-sensitivity-label-full.png)

    > [!NOTE]
    > 既定では、テナントにはラベルはありません。作成する必要があります。 こちらに例示した図のラベルには、[Azure Information Protection から移行](/azure/information-protection/configure-policy-migrate-labels) された既定のラベルが表示されます。

3. **[このラベルのスコープを定義する]** ページで、選択したオプションによって、構成できる設定のラベルのスコープと、公開時に表示される場所が決まります。

    ![機密度ラベルのスコープ。](../media/sensitivity-labels-scopes.png)

    - **[ファイルとメール]** が選択されている場合、Office Word や Outlook などの機密度ラベルをサポートするアプリに適用される設定を構成できます。 このオプションが選択されていない場合、これらの設定の最初のページを表示しても、それらを構成することはできず、ユーザーがこれらのアプリでラベルを選択することはできません。

    - **[グループとサイト]** が選択されている場合、Microsoft 365 グループ、および Teams と SharePoint のサイトに適用される設定を構成できます。 このオプションが選択されていない場合、これらの設定の最初のページを表示しても、それらを構成することはできず、ユーザーがグループおよびサイト用にラベルを選択することはできません。

    **スキーマ化されたデータ アセット** スコープの詳細については、「[Azure Purview のコンテンツに自動的にラベルを付ける](/azure/purview/create-sensitivity-label)」を参照 してください。

4. ラベルの設定には、構成の指示に従います。

    ラベル設定の詳細については、「概要」の「[秘密度ラベルでできること](sensitivity-labels.md#what-sensitivity-labels-can-do)」を参照してください。また、個々の設定については、UI のヘルプを参照してください。

5. これらの手順を繰り返して、さらにラベルを作成します。ただし、サブラベルを作成する場合は、まず親ラベルを選択してから、**[その他のアクション]** の [**...**] を選択し、**[サブラベルの追加]** を選択します。

6. 必要なすべてのラベルを作成したら、ラベルの順序を確認し、必要に応じて上下に移動します。 ラベルの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。 詳細については、概要の「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。

既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] ボタンを選択します。

![[ラベルの編集] ボタンを押して、秘密度ラベルを編集する。](../media/edit-sensitivity-label-full.png)

このボタンを選択すると、[**秘密度ラベルの編集**] 構成が起動し、手順 4 のすべてのラベル設定を変更できます。

ユーザーへの影響がどの程度かわからない場合は、ラベルを削除しないでください。 詳細については、「[ラベルの解除と削除](#removing-and-deleting-labels)」 のセクションを参照してください。 

> [!NOTE]
> ラベル ポリシーを使用して既に発行されているラベルを編集する場合、構成を終了するときに、追加の手順は必要ありません。 たとえば、同じユーザーに変更を反映させるために、ラベルを新しいラベル ポリシーに追加する必要はありません。 ただし、変更をすべてのアプリとサービスにレプリケートするには、最大で 24 時間かかります。

ラベルを発行するまで、アプリまたはサービスでラベルを選択することはできません。 ラベルを発行するには、ラベルを[ラベル ポリシーに追加](#publish-sensitivity-labels-by-creating-a-label-policy)する必要があります。

> [!IMPORTANT]
> この [**ラベル**] タブで、新しいラベル ポリシーを作成する必要がある場合を除き、[**ラベルの発行**] タブ (またはラベル編集時の [**ラベルの発行**] ボタン) を選択しないでください。 複数のラベル ポリシーが必要になるのは、ユーザーが異なるラベルまたは異なるポリシー設定を必要とする場合だけです。 ラベルポリシーをできるだけ少なくすることを目指してください。組織のラベルポリシーを1つだけにすることも珍しくありません。

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a>セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル設定

[セキュリティ/コンプライアンス センターの PowerShell](/powershell/exchange/scc-powershell) の [Set-Label](/powershell/module/exchange/set-label) コマンドレットを使ってその他のラベル設定を使用できます。

例として以下のようなものがあります。

- ユーザーがローカル言語でラベル名とヒントを表示できるように、多国籍の展開では *LocaleSettings* パラメーターを使用します。 [次のセクション](#example-configuration-to-configure-a-sensitivity-label-for-different-languages)には、フランス語、イタリア語、ドイツ語のラベル名とヒントのテキストを指定する設定例があります。

- Azure Information Protection 統合ラベル付けクライアントは、ラベルの色の設定やラベルの適用時のカスタム プロパティの適用など、[高度な設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)の広範な一覧をサポートします。 完全なリストについては、このクライアントの管理ガイドの「[利用できるラベルの詳細設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)」を参照してください。

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a>異なる言語向けに機密ラベルを構成する構成例

次の例では、ヒント用のプレースホルダー テキストが含まれる "Public" という名前のラベルの PowerShell 構成を示します。 この例では、ラベル名とヒントのテキストがフランス語、イタリア語、ドイツ語用に構成されています。

この構成の結果、これらの表示言語を使用する Office アプリを所有するユーザーには、ラベル名とツールヒントが同じ言語で表示されるようになります。 同様に、ファイルへのラベル付けをエクスプローラーから行うために Azure Information Protection 統一ラベル付けクライアントがインストールされている場合、これらの言語バージョンの Windows を所有しているユーザーがラベル付けのために右クリック アクションを使用すると、ラベル名とツールヒントがローカル言語で表示されます。

サポートする必要がある言語については、Office の[言語識別子](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (言語タグとも呼ばれます) を使用して、ラベル名とツールヒントの独自の翻訳を指定します。

PowerShell でコマンドを実行する前に、最初に[セキュリティ/コンプライアンス センターの PowerShell に接続](/powershell/exchange/connect-to-scc-powershell)する必要があります。

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
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>ラベル ポリシーを作成して秘密度ラベルを発行する

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)から、**[ソリューション]** > **[Information Protection]** を選択します。
    
    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。

2. [**ラベル ポリシー**] タブ、[**ラベルの発行**] の順に選択して、[**ポリシーの作成**] 構成を開始してください。

    たとえば、Microsoft 365 コンプライアンス センターでは、次のようになります。

    ![ラベルを発行。](../media/publish-sensitivity-labels-full.png)

    > [!NOTE]
    > 既定では、テナントにはラベル ポリシーはありません。作成する必要があります。 

3. **[発行する秘密度ラベルの選択]** ページで、**[発行する秘密度ラベルの選択]** リンクを選択します。 アプリとサービスで使用するラベルを選択し、[**追加**] を選択します。

    > [!IMPORTANT]
    > サブラベルを選択する場合は、必ず親ラベルも選択してください。

4. 選択したラベルを確認し、変更を加えるには、**[編集]** を選択します。それ以外の場合 **[次へ]** を選択します。

5. 指示に従ってポリシー設定を構成します。

    表示されるポリシー設定は、選択したラベルのスコープと一致します。 たとえば、**[ファイルとメール]** のスコープのみを持つラベルを選択した場合、ポリシー設定 **[このラベルを既定でグループとサイトに適用する]** および **[ユーザーにグループやサイトにラベルを付けるように要求する]** は表示されません。

    これらの設定の詳細については、概要情報の「[ラベル ポリシーでできること](sensitivity-labels.md#what-label-policies-can-do)」を参照してください。また、個々の設定については、UI のヘルプを参照してください。

    **Azure Purview assets (プレビュー) に構成されているラベルの場合**: これらのラベルには関連付けられたポリシー設定はありません。

6. 異なるユーザーやスコープに対して、異なるポリシー設定が必要な場合は、次の手順を繰り返します。 たとえば、ユーザーのグループにラベルを追加したり、ユーザーのサブセットに別の既定のラベルを作成したりできます。 または、異なるスコープを持つようにラベルを構成した場合です。

7. 複数のラベル ポリシーを作成すると、ユーザーの競合が発生することがあります。ポリシーの順序を確認し、必要に応じてこれらを上下に移動します。 ラベル ポリシーの順序を変更するには、[**その他のアクション**] の [**...**] を選択して、[**上へ移動**] または [**下へ移動**] を選択します。 詳細については、概要の「[ラベル ポリシーの優先度 (順序の問題)](sensitivity-labels.md#label-policy-priority-order-matters)」を参照してください。

[**ポリシーの作成**] 構成を完了すると、ラベル ポリシーが自動的に発行されます。 発行したポリシーは、簡単に編集して変更することができます。 特定の発行や再発行のアクションを選択する必要はありません。

既存のラベル ポリシーを編集するには、目的のラベル ポリシーを選択し、[**ポリシーの編集**] ボタンを選択します。 

![秘密度ラベルを編集する。](../media/edit-sensitivity-label-policy-full.png)

このボタンを選択すると、[**ポリシーの作成**] 構成が起動し、含めるラベルとラベルの設定を編集できます。 構成を完了すると、選択したユーザーとサービスに変更が自動的にレプリケートされます。

Windows、macOS、iOS、Android の Office アプリに組み込みのラベル付けを使用すると、ユーザーには 4 時間以内に新しいラベルが表示されます。web 上のWord、Excel、PowerPoint の場合は更新を行ってから 1 時間以内に新しいラベルが表示されます。ただし、変更がすべてのアプリとサービスに複製されるまでに最大 24 時間かかります。

機密ラベルをサポートする他のアプリやサービスは、独自の更新スケジュールとポリシー更新のトリガーを使用して、24 時間以上頻繁に更新される場合があります。 詳細については、ドキュメントを確認してください。 たとえば、Azure Information Protection 統合ラベル付けクライアントの場合は、「[Azure Information Protection クライアントの詳細な比較](/azure/information-protection/rms-client/use-client#detailed-comparisons-for-the-azure-information-protection-clients)」表の「**ポリシーの更新**」行を参照してください。

> [!TIP]
> 機密ラベルとラベル ポリシーの動作が期待よりも遅れる可能性があるタイミングの依存関係を考慮に入れる必要があります。 たとえば、暗号化を適用するラベルに対して [Azure Information Protection](/azure/information-protection/prepare#group-membership-caching-by-azure-information-protection) サービスによる新しいグループおよびグループ メンバーシップの変更、ネットワーク レプリケーションの待機時間と帯域幅制限、およびグループ メンバーシップのキャッシュを設定します。
> 
> それぞれ独自のタイミング サイクルを持つ多くの外部依存関係では、最近の変更に対するラベルとラベル ポリシーのトラブルシューティングを実施する前に 24 時間待機することをお考えください。

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a>セキュリティ/コンプライアンス センターの PowerShell を含むその他のラベル ポリシー設定

[セキュリティ/コンプライアンス センター](/powershell/exchange/scc-powershell) PowerShell の [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) コマンドレットを使用すると、追加のラベルポリシー設定を利用できます。

Azure Information Protection の統合ラベル付けクライアントは、他のラベリング ソリューションからの移行や、送信されるメールを警告、正当化、またはブロックする Outlook のポップアップ メッセージなど、多くの[詳細設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)をサポートしています。 完全なリストについては、このクライアントの管理ガイドの [[利用できるラベルの詳細設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)] を参照してください。

## <a name="use-powershell-for-sensitivity-labels-and-their-policies"></a>機密ラベルとそのポリシーに PowerShell を使用する

[セキュリティ / コンプライアンスセンター PowerShell](/powershell/exchange/scc-powershell) を使用して、ラベル管理センターに表示されるすべての設定を作成し、構成できるようになりました。 つまり、ラベル管理センターでは使用できない設定に PowerShell を使用することに加えて、機密ラベルと機密ラベルポリシーの作成とメンテナンスを完全にスクリプト化できるようになりました。 

サポートされるパラメーターと値については、次のドキュメントを参照してください。

- [New-Label](/powershell/module/exchange/new-label)
- [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy)
- [Set-Label](/powershell/module/exchange/set-label)
- [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy)

機密ラベルまたは機密ラベルポリシーの削除をスクリプト化する必要がある場合は、 [Remove-Label](/powershell/module/exchange/remove-label) および [Remove-LabelPolicy](/powershell/module/exchange/remove-labelpolicy) を使用することもできます。 ただし、機密ラベルを削除する前に、次のセクションを必ずお読みください。

## <a name="removing-and-deleting-labels"></a>ラベルの解除と削除

運用環境では、通常、ラベル ポリシーから秘密度ラベルを解除したり、秘密度ラベルを削除したりする必要はありません。 テストの初期段階では、そのいずれかまたは両方の操作を行う必要が発生する可能性が高いかもしれません。 それらの操作を行った場合、何が起こるかをよく理解しておいてください。

ラベル ポリシーからのラベルの解除は、削除に比べてリスクが少なく、必要に応じて後でいつでもラベル ポリシーに戻すことができます。

- ラベル ポリシーからラベルを解除して当初指定したユーザーにラベルが発行されないようになった場合、次にラベル ポリシーが更新されるときに、そのラベルは Office アプリの選択対象としてユーザーに表示されなくなります。 ただし、ラベルがドキュメントやメールに適用されている場合は、そのコンテンツからはラベルは解除されません。 ラベルによって適用された暗号化があればそのまま残り、基となる保護テンプレートは発行済のまま維持されます。 

- 解除されたラベルが、以前にコンテンツに適用されていた場合、Word、Excel、PowerPoint の組み込みラベルを使っているユーザーに対しては、適用されたラベルは引き続きステータス バーに表示されます。 同様に、SharePoint サイトに適用されている解除済みのラベルも **秘密度** 列のラベル名に表示されます。

これに対して、ラベルを削除した場合は次のようになります:

- ラベルが暗号化を適用している場合、以前に保護したコンテンツを引き続き開けるようにするため、基になる保護テンプレートはアーカイブされます。 これはアーカイブされた保護テンプレートなので、新しいラベルを同じ名前で作成することはできません。 [PowerShell](/powershell/module/aipservice/remove-aipservicetemplate) を使って保護テンプレートを削除することはできますが、アーカイブしたテンプレートを使用して暗号化されたコンテンツを開く必要がないことが確実な場合を除いて、この操作は実行しないでください。

- デスクトップ アプリの場合: メタデータのラベル情報は残りますが、名前のマッピングに使うラベル ID は利用できなくなっているため、適用されたラベル名は表示されず (ステータス バーなどに)、これによりユーザーはコンテンツはラベル付けされていないと判断します。 ラベルが暗号化を行っている場合、暗号化はそのまま行われ、コンテンツが開かれると、既にアーカイブされている保護テンプレートの名前と説明が表示されます。

- Office on the web の場合: ステータス バーまたは **秘密度** 列にラベル名は表示されません。 ラベルが暗号化を適用していない場合にのみ、メタデータのラベル情報はそのまま残ります。 ラベルが暗号化を適用していて、[SharePoint と OneDrive の秘密度ラベル](sensitivity-labels-sharepoint-onedrive-files.md)が有効になっている場合、メタデータのラベル情報は削除され、暗号化は解除されます。 

ラベルポリシーから秘密度ラベルを削除したり、秘密度ラベルを削除したりすると、これらの変更がすべてのユーザーとサービスに複製されるまでに最大 24 時間かかることがあります。

## <a name="next-steps"></a>次の手順

特定のシナリオで秘密度ラベルを構成して使用するには、次の記事を参照してください。

- [機密ラベルでの暗号化を使用してコンテンツへのアクセスを制限する](encryption-sensitivity-labels.md)

- [機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)

- [チーム、グループ、およびサイトで機密度ラベルを使用する](sensitivity-labels-teams-groups-sites.md)

- [SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)

ラベルの使用状況を監視するには、「[データ分類の使用を開始する](data-classification-overview.md)」を参照してください。
