---
title: データ損失防止のオンプレミス スキャナーの使用を開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: データ損失防止のオンプレミス スキャナーを設定する
ms.openlocfilehash: a1bcebfb48a502a9d7c484d266d91fe105603f84
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625437"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner"></a>データ損失防止のオンプレミス スキャナーの使用を開始する

この記事では、Microsoft Purview データ損失防止オンプレミス スキャナーの前提条件と構成について説明します。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

DLP オンプレミス スキャナーの使用を開始する前に、[Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) およびアドオンを確認する必要があります。 DLP ルールを設定する管理者アカウントに次のライセンスのいずれかを割り当てる必要があります:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft 365 E5 情報保護およびガバナンス 


ライセンスの詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。

> [!IMPORTANT]
> ファイルの追加またはファイルの使用によってスキャンされた場所に貢献するすべてのユーザーには、スキャナー ユーザーだけでなくライセンスが必要です。

### <a name="permissions"></a>アクセス許可

Endpoint DLP からのデータは、[アクティビティ エクスプローラー](data-classification-activity-explorer.md)で表示します。 Activity エクスプローラーに権限を付与する役割は4つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。

- グローバル管理者
- コンプライアンス管理者
- セキュリティ管理者
- コンプライアンス データ管理者

#### <a name="roles-and-role-groups-in-preview"></a>プレビュー段階の [役割と役割グループ]

プレビューには、アクセス制御を微調整するためにテストできる役割と役割グループがあります。

プレビュー段階の該当する役割の一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)」を参照してください。

- Information Protection 管理者
- Information Protection アナリスト
- Information Protection 調査員
- Information Protection 閲覧者

プレビュー段階の該当する役割グループの一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割グループ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)」を参照してください。

- 情報保護
- Information Protection レベル
- Information Protection アナリスト
- Information Protection 調査担当者
- Information Protection 閲覧者

### <a name="dlp-on-premises-scanner-prerequisites"></a>DLP オンプレミス スキャナーの前提条件

- Azure Information Protection (AIP) スキャナーは、DLP ポリシーの一致とポリシーの適用を実装します。スキャナーは AIP クライアントの一部としてインストールされるため、インストールは AIP、AIP クライアント、および AIP 統合ラベル スキャナーのすべての前提条件を満たしている必要があります。
- [AIP 統合ラベル クライアントのインストール](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)と [] の詳細については、「[Azure Information Protection 統合ラベルスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)」を参照してください。
- すべての検出ルールが機密情報タイプのみに基づいている場合でも、テナントには少なくとも 1 つのラベルとポリシーが公開されている必要があります。

## <a name="deploy-the-dlp-on-premises-scanner"></a>DLP オンプレミス スキャナーを展開する

1. [AIP 統合ラベル クライアントのインストール](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)の手順に従います。 
2. 「[Azure Information Protection 統合ラベルスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)」の手順に従って、スキャナーのインストールを完了します。
    1. ネットワーク検出ジョブの構成はオプションの手順です。 これをスキップして、コンテンツ スキャン ジョブでスキャンする特定のリポジトリを定義できます。
    2. コンテンツ スキャン ジョブを作成し、DLP エンジンによる評価が必要なファイルをホストするリポジトリを指定する必要があります。
    3. 作成したコンテンツ スキャン ジョブで DLP ルールを有効にし、DLP 有効化段階に直接進む場合を除いて、**[有効にする]** オプションを **[オフ]** に設定します。
3. コンテンツ スキャン ジョブが適切なクラスターに割り当てられていることを確認します。それでもコンテンツ スキャン ジョブを作成しなかった場合は、新しいジョブを作成して、スキャナー ノードを含むクラスターに割り当てます。

4. [Azure ポータルの Azure Information Protection](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) 拡張機能に接続し、スキャンを実行するコンテンツ スキャン ジョブにリポジトリを追加します。

5. 次のいずれかの操作を実行して、スキャンを実行します。 
    1. スキャナーのスケジュールを設定する
    1. ポータルで手動の **[今すぐスキャン]** オプションを使用する
    1. または、**Start-AIPScan** PowerShell コマンドレットを実行します

   > [!IMPORTANT]
   > スキャナーはデフォルトでリポジトリのデルタ スキャンを実行し、ファイルが変更されたか、完全な再スキャンを開始しない限り、前のスキャン サイクルですでにスキャンされたファイルはスキップされることに注意してください。完全な再スキャンは、UI の **[すべてのファイルを再スキャンする]** オプションを使用するか、**Start-AIPScan-Reset** を実行することで開始できます。

6.  Microsoft Purview コンプライアンス ポータルの[データ損失防止ページ](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開きます。

7. **[ポリシーの作成]** を選択し、テスト DLP ポリシーを作成します。 ポリシーの作成についてサポートが必要な場合は、「[テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)」を参照してください。 この機能に慣れるまで、必ずテストで実行してください。 ポリシーには、次のパラメータを使用します。
    1. 必要に応じて、DLP オンプレミス スキャナー ルールを特定の場所にスコープします。 **[場所]** のスコープを **[すべて]** に設定すると、スキャナーによってスキャンされたすべてのファイルが DLP ルールの照合と適用の対象になります。
    1. 場所を指定するときは、除外リストまたは包含リストのいずれかを使用できます。 ルールは、包含リストにリストされているパターンの 1 つに一致するパスにのみ関連するか、包含リストにリストされているパターンに一致するファイルを除くすべてのファイルに関連するように定義できます。 ローカル パスはサポートされていません。 有効なパスの例を次に示します。
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. 許容できない値の使用例を次に示します。
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> 除外リストは、包含リストよりも優先されます。

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>DLP アラート管理ダッシュボードでの DLP オンプレミス スキャナー アラートの表示

1. Microsoft Purview コンプライアンス ポータルの [データ損失防止ページ](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開き、**アラート** を選択します。

2. エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>アクティビティ エクスプローラーと監査ログでの DLP オンプレミス スキャナーの表示

> [!NOTE]
> オンプレミス スキャナーでは、監査を有効にする必要があります。 Microsoft 365では、監査は既定で有効になっています。

1. Microsoft Purview コンプライアンス ポータルでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。

2. オンプレミス スキャナーの場所のすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。

3. [[コンプライアンス センターの監査ログ]](https://security.microsoft.com/auditlogsearch) を開きます。 DLP ルールの一致は監査ログ UI で利用可能であるか、[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell からアクセスできます。 


## <a name="next-steps"></a>次のステップ
DLP オンプレミス の場所のテスト ポリシーを展開し、アクティビティ エクスプローラーでアクティビティ データを表示できるようになったので、機密アイテムを保護する DLP ポリシーを作成する次のステップに進む準備ができました。

- [DLP オンプレミスの使用](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>関連項目

- [DLP オンプレミス スキャナーの詳細情報](dlp-on-premises-scanner-learn.md)
- [DLP オンプレミス スキャナーの使用](dlp-on-premises-scanner-use.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
