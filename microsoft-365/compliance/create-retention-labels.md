---
title: 保持ラベルを作成、発行、および自動適用する
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
description: 必要なものを保持し、不要なものを削除し、Office 365 環境でアイテムをレコードとして宣言するための、保持ラベルの作成、発行、および自動適用の手順。
ms.openlocfilehash: 65319baa0fd238ebdc403307fb8bb91a59d87cd6
ms.sourcegitcommit: 3cd487476efe4138d1b42499fbffbbe4bacfe5b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "44408469"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a>保持ラベルを作成、発行、および自動適用する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

次の情報を使用して、[保持ラベル](labels.md)を作成し、ドキュメントやメールに自動的に適用するか、ユーザーが手動で適用できるように公開します。

保持ラベルは、必要なものを保持し、不要なものを削除するのに役立ちます。 また、Microsoft 365 データの[レコード管理](records-management.md)ソリューションの一部として、アイテムをレコードとして宣言するためにも使用されます。

保持ラベルを作成して構成する場所は、レコード管理を使用しているかどうかによって異なります。 手順は両方のシナリオに提供されます。

## <a name="before-you-begin"></a>はじめに

保持ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ &amp; コンプライアンス センターにアクセスする許可が必要です。 テナント管理者は、規定でこの場所にアクセスできるため、法令遵守責任者や他のユーザーにセキュリティ &amp; コンプライアンス センターへのアクセス権を付与できます。テナント管理者が持つすべてのアクセス許可を付与する必要はありません。これを行うには、セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページに移動して、[**コンプライアンス管理者**] 役割グループを編集し、その役割グループにメンバーを追加することをお勧めします。 
  
詳細については、「[ユーザーに Office 365 セキュリティ センター/コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。
  
これらのアクセス許可は、保持ラベルとラベル ポリシーを作成して適用するときにのみ必要になります。ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。

## <a name="create-and-configure-retention-labels"></a>保持ラベルを作成して構成する

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。
    
    - レコード管理を使用している場合:
        - [**ソリューション**] > [**レコード管理**] > [**ファイル計画**] タブ > [**+ラベルを作成**] > [**保持ラベル**]
        
    - レコード管理を使用していない場合:
       - [**ソリューション**] > [**情報ガバナンス**] > [**ラベル**] タブ > + [**ラベルを作成**]
    
    すぐにオプションが表示されませんか? 最初に [**すべて表示**] を選択します。 

2. ウィザードでプロンプトに従います。 レコード管理を使用している場合:
    
    - ファイル計画記述子については、「[ファイル計画マネージャーの概要](file-plan-manager.md)」をご覧ください。
    
    - 保持ラベルを使用してコンテンツをレコードとして宣言するには、[**このラベルを使用して、コンテンツを「レコード」に分類する**] チェックボックスをオンにします。

3. さらにラベルを作成するには、これらの手順を繰り返します。

既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] を選択します。 これにより同じウィザードが起動し、手順 2 でラベルの説明と設定を変更できます。

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a>保持ラベル ポリシーを作成して保持ラベルを発行する

保持ラベルを発行して、ユーザーが手動で適用できるようにします。

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。
    
    - レコード管理を使用している場合:
        - [**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**ラベルの発行**]
    
    - レコード管理を使用していない場合:
        - [**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**ラベルの発行**]
    
    すぐにオプションが表示されませんか? 最初に [**すべて表示**] を選択します。 

2. ウィザードでプロンプトに従います。
    
    保持ラベルでサポートされている場所については、「[保持ラベルと場所](labels.md#retention-label-policies-and-locations)」のセクションをご覧ください。 

## <a name="auto-apply-a-retention-label"></a>自動適用の保持ラベル

指定した条件に基づいて、保持ラベルを自動的に適用します。

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。
    
    - レコード管理を使用している場合: **情報ガバナンス**:
        - [**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]
    
    - レコード管理を使用していない場合:
        - [**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]
    
    すぐにオプションが表示されませんか? 最初に [**すべて表示**] を選択します。 

2. ウィザードでプロンプトに従います。
    
    保持ラベルを自動的に適用する条件の構成については、このページの「[自動適用の保持ラベルの条件の構成](#configuring-conditions-for-auto-apply-retention-labels)」セクションをご覧ください。
    
    保持ラベルでサポートされている場所については、「[保持ラベルと場所](labels.md#retention-label-policies-and-locations)」のセクションをご覧ください。


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a>自動適用の保持ラベルの条件の構成

コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用できます。
  
- [特定の種類の機密情報](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [作成したクエリに一致する特定のキーワード](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [トレーニング可能な分類子の一致](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動適用ラベルの [条件選択] ページ](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

構成した条件に一致するすべてのコンテンツに保持ラベルを自動的に適用するには、最大 7 日かかります。

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>特定の種類の機密情報によるコンテンツへのラベルの自動適用

機密情報用に自動適用の保持ラベルを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。 各ポリシー テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。 たとえば、次に示すテンプレートは、米国の ITIN、SSN、パスポート番号を探します。 DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。
  
![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
ポリシー テンプレートを選択すると、すべての種類の機密情報を追加または削除したり、インスタンス数と一致精度を変更したりできます。ここに示す例では、保持ラベルは次の場合にのみ自動的に適用されます。
  
- コンテンツに、次の 3 種類の機密情報のいずれかに 1 から 9 個のインスタンスが含まれる場合。**最大** 値を削除して、**任意** の値に変更できます。
    
- 検出された機密情報の種類は、一致精度 (または信頼レベル) が少なくとも 75 に設定されています。多くの機密情報の種類は複数のパターンで定義されています。一致精度の高いパターンでは、より多くの証拠 (キーワード、日付、アドレスなど) が検索される必要がありますが、一致精度の低いパターンでは必要な証拠は少なくなります。簡単に言えば、一致精度の **最小** 値が低いほど、コンテンツは条件に一致しやすくなります。 
    
これらのオプションの詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」をご覧ください。
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル

特定の条件を満たすコンテンツにラベルを自動的に適用できます。現在利用可能な条件では、特定の単語、フレーズ、または検索可能なプロパティの値を含むコンテンツへのラベルの適用がサポートされています。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。

クエリ構文の詳細については、次を参照してください。

- [キーワード クエリ言語 (KQL) 構文のリファレンス](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

クエリ ベースのラベルは検索インデックスを使用してコンテンツを特定します。有効な検索可能なプロパティの詳細については、以下を参照してください。

- [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
- [クロールされたプロパティと管理プロパティの概要 (SharePoint Server)](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

クエリの例:

- Exchange
    - subject:"Quarterly Financials"
    - 受信者: garthf<!--nolink-->@contoso.com
- SharePoint および OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![クエリ エディター](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する

トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。 組み込み分類子には、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および**脅威**が含まれます。

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

このオプションを使用してラベルを自動的に適用するには、SharePoint Online サイトとメールボックスには少なくとも 10 MB のデータが必要です。

トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。

構成の例については、「[組み込みの分類子を準備して使用する方法](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)」を参照してください。

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>保持ラベルが有効になるまでの所要時間

保持ラベルを発行または自動適用しても、すぐには有効になりません。
  
1. まず、ラベル ポリシーを管理センターからポリシー内の場所に同期させる必要があります。
    
2. また、発行された保持ラベルをエンド ユーザーが利用したり、ラベルをコンテンツに自動適用したりできるようになるまでには、場所で時間がかかることがあります。 これにかかる時間は、場所と保持ラベルの種類によって異なります。
    
### <a name="published-retention-labels"></a>発行された保持ラベル

SharePoint または OneDrive に保持ラベルを発行する場合、保持ラベルがエンド ユーザーに表示されるまでに 1 日かかる場合があります。また、Exchange に保持ラベルを発行する場合は、保持ラベルがエンド ユーザーに表示するまでに 7 日間かかる場合があり、さらにメールボックスには少なくとも 10 MB のデータが含まれている必要があります。
  
![手動ラベルが有効になるタイミングの図](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>自動適用の保持ラベル

特定の条件に一致するコンテンツに保持ラベルを自動適用する場合、条件に一致するすべての既存コンテンツに保持ラベルが適用されるまでに 7 日間かかります。
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Exchange に発行された保持ラベルの状態を確認する方法

Exchange Online では、7 日ごとにプロセスが実行され、保持ラベルがエンド ユーザーに表示されます。 PowerShell を使用することで、このプロセスが最後に実行された日時を確認できるため、いつ実行されるかを特定できます。
  
1. [Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=799773)。
    
2. これらのコマンドを実行します。
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

結果の中で、`ELCLastSuccessTimeStamp` (UTC) プロパティは、システムがメールボックスを最後に処理した日時を示しています。 ポリシーの作成後に処理がまだ行われていない場合は、ラベルは表示されません。 処理を強制的に行うには、`Start-ManagedFolderAssistant -Identity <user>` を実行します。
    
Outlook on the web にラベルが表示されると思われるにもかかわらず、ラベルが表示されない場合は、ブラウザーのキャッシュを必ず消去してください (CTRL + F5)。
    

## <a name="updating-retention-labels-and-their-policies"></a>保持ラベルとそのポリシーの更新

保持ラベル、保持ラベル ポリシー、または自動適用ポリシーを編集し、保持ラベルが既にコンテンツに適用されている場合、更新された設定は、新しくラベル付けされたコンテンツに加えて、このコンテンツに自動的に適用されます。

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a>保持ラベルの PowerShell コマンドレットを検索する

保持ラベルのコマンドレットを使用するには:
  
1. [Office 365 セキュリティ センターとコンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. 以下の Office 365 セキュリティ センターとコンプライアンス センターのコマンドレットの使用
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
