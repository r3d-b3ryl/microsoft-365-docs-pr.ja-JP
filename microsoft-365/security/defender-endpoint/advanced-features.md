---
title: Microsoft Defender for Endpointで高度な機能を構成する
description: Microsoft Defender for Endpointでブロック ファイルなどの高度な機能を有効にします。
keywords: 高度な機能, 設定, ブロック ファイル, 自動調査, 自動解決, skype, MICROSOFT Defender for IDENTITY, office 365, Azure Information Protection, intune
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
ms.openlocfilehash: ac43b62c16cd3e1394cec7a1a75e69bf613757ef
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64934337"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Defender for Endpoint で高度な機能を構成する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedfeats-abovefoldlink)

使用する Microsoft セキュリティ製品によっては、Defender for Endpoint を統合するための高度な機能がいくつかあります。

## <a name="enable-advanced-features"></a>高度な機能を有効にする

1. ナビゲーション ウィンドウで、[**エンドポイント** \> **の高度な機能****設定**\>選択します。
2. 構成する高度な機能を選択し、オンと **オフ****の設定を** 切り替えます。
3. [ **保存] 環境設定をクリックします**。

次の高度な機能を使用して、悪意のある可能性のあるファイルから保護を強化し、セキュリティ調査中に洞察を得ます。

## <a name="automated-investigation"></a>自動調査

この機能を有効にすると、サービスの自動調査機能と修復機能を利用できます。 詳細については、「 [自動調査](automated-investigations.md)」を参照してください。

## <a name="live-response"></a>ライブ応答

> [!NOTE]
> ライブ応答を有効にするには、Microsoft Defender for Endpoint ポータルの [詳細設定] セクションで自動 **調査** を有効にする必要があります。

適切なアクセス許可を持つユーザーがデバイスでライブ応答セッションを開始できるように、この機能をオンにします。

ロールの割り当ての詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。

## <a name="live-response-for-servers"></a>サーバーのライブ応答

適切なアクセス許可を持つユーザーがサーバーでライブ応答セッションを開始できるように、この機能をオンにします。

ロールの割り当ての詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。

## <a name="live-response-unsigned-script-execution"></a>ライブ応答の署名されていないスクリプトの実行

この機能を有効にすると、ライブ応答セッションで署名されていないスクリプトを実行できます。

## <a name="always-remediate-pua"></a>PUA を常に修復する

望ましくない可能性があるアプリケーション (PUA) は、コンピューターの実行速度が低下したり、予期しない広告を表示したり、最悪の場合は他のソフトウェアをインストールしたりするソフトウェアのカテゴリです。これは、予期しないソフトウェアや望ましくない可能性があります。

PUA 保護がデバイスで構成されていない場合でも、不要な可能性があるアプリケーション (PUA) がテナント内のすべてのデバイスで修復されるようにするには、この機能をオンにします。 この機能のアクティブ化は、ユーザーがデバイスに不要なアプリケーションを誤ってインストールするのを防ぎます。 オフにすると、修復はデバイスの構成に依存します。

## <a name="restrict-correlation-to-within-scoped-device-groups"></a>スコープ付きデバイス グループ内への関連付けの制限

この構成は、ローカル SOC 操作で、アクセスできるデバイス グループのみにアラートの相関関係を制限するシナリオに使用できます。 この設定をオンにすると、デバイス間グループが 1 つのインシデントと見なされなくなったアラートで構成されるインシデントが発生します。 ローカル SOC は、関連するデバイス グループのいずれかにアクセスできるため、インシデントに対してアクションを実行できます。 ただし、グローバル SOC では、1 つのインシデントではなく、デバイス グループごとに複数の異なるインシデントが表示されます。 組織全体のインシデントの相関関係の利点を上回る場合を除き、この設定をオンにすることはお勧めしません。

> [!NOTE]
> この設定を変更すると、今後のアラートの相関関係にのみ影響します。

## <a name="enable-edr-in-block-mode"></a>ブロック モードでEDRを有効にする

ブロック モードのエンドポイントの検出と応答 (EDR) は、パッシブ モードで実行されている場合でも、悪意のあるアーティファクトから保護Microsoft Defender ウイルス対策提供します。 オンにすると、ブロック モードでEDRすると、デバイスで検出された悪意のある成果物や動作がブロックされます。 ブロック モードのEDRは、侵害後に検出された悪意のある成果物を修復するためにバックグラウンドで機能します。

## <a name="autoresolve-remediated-alerts"></a>自動解決で修復されたアラート

Windows 10 Version 1809以降に作成されたテナントの場合、自動調査と修復機能は既定で構成され、自動分析結果の状態が "脅威が見つかりません" または "修復済み" であるアラートが解決されます。 アラートを自動的に解決したくない場合は、手動で機能をオフにする必要があります。

> [!TIP]
> そのバージョンより前に作成されたテナントの場合は、[ [高度な](https://security.microsoft.com//preferences2/integration) 機能] ページでこの機能を手動で有効にする必要があります。

> [!NOTE]
>
> - 自動解決アクションの結果は、デバイスで検出されたアクティブなアラートに基づくデバイス リスク レベルの計算に影響を与える可能性があります。
> - セキュリティ運用アナリストがアラートの状態を手動で "進行中" または "解決済み" に設定した場合、自動解決機能によって上書きされることはありません。

## <a name="allow-or-block-file"></a>ファイルを許可またはブロックする

ブロックは、組織が次の要件を満たしている場合にのみ使用できます。

- Microsoft Defender ウイルス対策をアクティブなマルウェア対策ソリューションとして使用し、
- クラウドベースの保護機能が有効になっている

この機能を使用すると、ネットワーク内の悪意のある可能性のあるファイルをブロックできます。 ファイルをブロックすると、組織内のデバイスで読み取り、書き込み、または実行できなくなります。

ファイルの **許可またはブロック** を有効にするには:

1. ナビゲーション ウィンドウで、[**Endpoints** \> **General** \> **Advanced features** \> **Allow or block file**] **設定**\>選択します。

1. **オン** と **オフ** の設定を切り替えます。
 
    :::image type="content" source="../../media/alloworblockfile.png" alt-text="[エンドポイント] 画面" lightbox="../../media/alloworblockfile.png":::

1. ページの下部にある [ **保存] 設定** を選択します。

この機能を有効にすると、ファイルのプロファイル ページの [**インジケーターの追加**] タブでファイルを [ブロック](respond-file-alerts.md#allow-or-block-file)できます。

## <a name="custom-network-indicators"></a>カスタム ネットワーク インジケーター

この機能を有効にすると、IP アドレス、ドメイン、または URL のインジケーターを作成できます。これにより、カスタム インジケーター リストに基づいて許可またはブロックされるかどうかを決定できます。

この機能を使用するには、デバイスがバージョン 1709 以降Windows 10実行されているか、Windows 11されている必要があります。 また、ブロック モードでネットワーク保護を行う必要があり、マルウェア対策プラットフォームのバージョン 4.18.1906.3 以降 [では KB 4052623を参照してください](https://go.microsoft.com/fwlink/?linkid=2099834)。

詳細については、「インジケーターの [管理](manage-indicators.md)」を参照してください。

> [!NOTE]
> ネットワーク保護は、Defender for Endpoint データ用に選択した場所の外部にある可能性がある場所で要求を処理する評判サービスを利用します。

## <a name="tamper-protection"></a>改ざん防止
一部の種類のサイバー攻撃では、悪いアクターがマシンでウイルス対策などのセキュリティ機能を無効にしようとします。 悪意のあるアクターは、データへのアクセスを容易にしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にすることを好みます。

改ざん防止は、本質的にMicrosoft Defender ウイルス対策をロックし、アプリやメソッドを通じてセキュリティ設定が変更されないようにします。

この機能は、組織がMicrosoft Defender ウイルス対策を使用し、クラウドベースの保護が有効になっている場合に使用できます。 詳細については、「[クラウド配信保護を通じてMicrosoft Defender ウイルス対策で次世代テクノロジを使用](cloud-protection-microsoft-defender-antivirus.md)する」を参照してください。

改ざん防止を有効にして、セキュリティ ソリューションとその本質的な機能に対する不要な変更を防ぎます。

## <a name="show-user-details"></a>ユーザーの詳細を表示する

Azure Active Directoryに格納されているユーザーの詳細を表示できるように、この機能を有効にします。 詳細には、ユーザー アカウント エンティティを調査するときのユーザーの画像、名前、タイトル、部署の情報が含まれます。 ユーザー アカウント情報は、次のビューで確認できます。

- セキュリティ運用ダッシュボード
- アラート キュー
- デバイスの詳細ページ

詳細については、「 [ユーザー アカウントを調査する](investigate-user.md)」を参照してください。

## <a name="skype-for-business-integration"></a>Skype for Business 統合

Skype for Business統合を有効にすると、Skype for Business、電子メール、または電話を使用してユーザーと通信できます。 このアクティブ化は、ユーザーと通信し、リスクを軽減する必要がある場合に便利です。

> [!NOTE]
> デバイスがネットワークから分離されている場合は、ユーザーがネットワークから切断されている間に通信を許可するOutlookとSkype通信を有効にすることを選択できるポップアップがあります。 この設定は、デバイスが分離モードの場合にSkype通信とOutlook通信に適用されます。

## <a name="microsoft-defender-for-identity-integration"></a>Microsoft Defender for Identity統合

Microsoft Defender for Identityとの統合により、別の Microsoft Identity セキュリティ製品に直接ピボットできます。 Microsoft Defender for Identityは、侵害された疑いのあるアカウントと関連リソースに関するより多くの分析情報を使用して調査を強化します。 この機能を有効にすると、特定の観点からネットワーク全体をピボットすることで、デバイスベースの調査機能を強化できます。

> [!NOTE]
> この機能を有効にするには、適切なライセンスが必要です。

## <a name="office-365-threat-intelligence-connection"></a>Office 365脅威インテリジェンス接続

この機能は、アクティブなOffice 365 E5または脅威インテリジェンス アドオンがある場合にのみ使用できます。 詳細については、Office 365 Enterprise E5 製品ページを参照してください。

この機能を有効にすると、Microsoft Defender for Office 365のデータをMicrosoft 365 Defenderに組み込み、Office 365 メールボックスとWindows デバイス全体で包括的なセキュリティ調査を行うことができます。

> [!NOTE]
> この機能を有効にするには、適切なライセンスが必要です。

Office 365脅威インテリジェンスでコンテキスト に応じたデバイス統合を受け取るには、セキュリティ & コンプライアンス ダッシュボードで Defender for Endpoint の設定を有効にする必要があります。 詳細については、「 [脅威の調査と対応](/microsoft-365/security/office-365-security/office-365-ti)」を参照してください。

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft 脅威エキスパート - 標的型攻撃通知

2 つの Microsoft Threat Expert コンポーネントのうち、対象となる攻撃通知は一般公開されています。 エキスパートオンデマンド機能はまだプレビュー段階です。 エキスパート オンデマンド機能は、プレビューに申請し、アプリケーションが承認されている場合にのみ使用できます。 Microsoft 脅威エキスパートから Defender for Endpoint ポータルのアラート ダッシュボードを介して、および構成した場合は電子メールで標的型攻撃通知を受け取ることができます。

> [!NOTE]
> Defender for Endpoint のMicrosoft 脅威エキスパート機能は、[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)の E5 ライセンスで使用できます。

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

この設定を有効にすると、Defender for Endpoint シグナルがMicrosoft Defender for Cloud Appsに転送され、クラウド アプリケーションの使用状況をより詳細に把握できるようになります。 転送されたデータは、Defender for Cloud Apps データと同じ場所に格納および処理されます。

> [!NOTE]
> この機能は、[Windows 10](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) バージョン 1709 (OS Build 16299.1085 with [KB4493441)、Windows 10、バージョン 1803 (KB4493464](https://support.microsoft.com/help/4493441) を使用した OS ビルド 17134.704)、Windows 10 Version 1809を実行しているデバイスで、Enterprise Mobility + Security用の E5 ライセンス[](https://support.microsoft.com/help/4493464)で使用できます。 ([KB4489899](https://support.microsoft.com/help/4489899) を使用した OS ビルド 17763.379)、以降のWindows 10 バージョン、またはWindows 11。

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Microsoft Defender for Identity ポータルからMicrosoft Defender for Endpoint統合を有効にする

Microsoft Defender for Identityでコンテキスト デバイスの統合を受け取るには、Microsoft Defender for Identity ポータルで機能を有効にする必要もあります。

1. グローバル管理者またはセキュリティ管理者ロールを[使用して、Microsoft Defender for Identity ポータル](https://portal.atp.azure.com/)にログインします。

2. **[インスタンスの作成**] をクリックします。

3. 統合設定を **[オン]** に切り替え、[ **保存]** をクリックします。

両方のポータルで統合手順を完了すると、関連するアラートがデバイスの詳細またはユーザーの詳細ページに表示されます。

## <a name="web-content-filtering"></a>Web コンテンツ フィルタリング

不要なコンテンツを含む Web サイトへのアクセスをブロックし、すべてのドメインで Web アクティビティを追跡します。 ブロックする Web コンテンツ カテゴリを指定するには、 [Web コンテンツ フィルター ポリシーを作成します](https://security.microsoft.com/preferences2/web_content_filtering_policy)。 [Microsoft Defender for Endpointセキュリティ ベースライン](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)をデプロイするときに、ブロック モードでネットワーク保護を行っていることを確認します。

## <a name="share-endpoint-alerts-with-microsoft-purview-compliance-portal"></a>Microsoft Purview コンプライアンス ポータルでエンドポイント アラートを共有する

エンドポイント のセキュリティ アラートとそのトリアージの状態を Microsoft Purview コンプライアンス ポータルに転送し、アラートを使用してインサイダー リスク管理ポリシーを強化し、内部リスクを修復して害を及ぼす前に対処できるようにします。 転送されたデータは処理され、Office 365 データと同じ場所に格納されます。

インサイダー リスク管理設定で [セキュリティ ポリシー違反インジケーター](/microsoft-365/compliance/insider-risk-management-settings#indicators) を構成した後、Defender for Endpoint アラートは、該当するユーザーのインサイダー リスク管理と共有されます。

## <a name="microsoft-intune-connection"></a>Microsoft Intune接続

Defender for Endpoint を[Microsoft Intune](/intune/what-is-intune)と統合して[、デバイスリスクベースの条件付きアクセスを有効にすることができます](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。 [この機能を有効にすると](configure-conditional-access.md)、Defender for Endpoint デバイス情報をIntuneと共有でき、ポリシーの適用が強化されます。

> [!IMPORTANT]
> この機能を使用するには、Intuneと Defender for Endpoint の両方で統合を有効にする必要があります。 特定の手順の詳細については、「 [Defender for Endpoint で条件付きアクセスを構成する」を参照してください](configure-conditional-access.md)。

この機能は、次の前提条件がある場合にのみ使用できます。

- Enterprise Mobility + Security E3およびWindows E5 (または E5 Microsoft 365 Enterprise) のライセンスを持つテナント
- アクティブなMicrosoft Intune環境。Intuneマネージド Windows デバイス[がAzure AD参加しています](/azure/active-directory/devices/concept-azure-ad-join/)。

### <a name="conditional-access-policy"></a>条件付きアクセス ポリシー

Intune統合を有効にすると、Intuneによって従来の条件付きアクセス (CA) ポリシーが自動的に作成されます。 このクラシック CA ポリシーは、状態レポートをIntuneに設定するための前提条件です。 削除しないでください。

> [!NOTE]
> Intuneによって作成されるクラシック CA ポリシーは、エンドポイントの構成に使用される最新[の条件付きアクセス ポリシー](/azure/active-directory/conditional-access/overview/)とは異なります。

## <a name="device-discovery"></a>デバイス検出

余分なアプライアンスや煩雑なプロセス変更を必要とせずに、会社のネットワークに接続されているアンマネージド デバイスを見つけるのに役立ちます。 オンボードされたデバイスを使用すると、ネットワーク内の管理されていないデバイスを見つけて、脆弱性とリスクを評価できます。 詳細については、「 [デバイスの検出」を](device-discovery.md)参照してください。

> [!NOTE]
> デバイス インベントリリストから管理されていないデバイスを除外するには、常にフィルターを適用できます。 また、API クエリのオンボード状態列を使用して、管理されていないデバイスを除外することもできます。

## <a name="preview-features"></a>プレビュー機能

Defender for Endpoint プレビュー リリースの新機能について説明します。 プレビュー エクスペリエンスをオンにして、今後の機能を試してください。

今後の機能にアクセスできます。これにより、機能が一般公開される前に全体的なエクスペリエンスを向上させるためのフィードバックを提供できます。

## <a name="download-quarantined-files"></a>検疫済みファイルをダウンロードする

検疫済みファイルをセキュリティで保護された準拠した場所にバックアップし、検疫から直接ダウンロードできるようにします。 **[ファイルのダウンロード**] ボタンは常にファイル ページで使用できます。 この設定は既定でオンになっています。 [要件の詳細を確認する](respond-file-alerts.md#download-quarantined-files)

## <a name="related-topics"></a>関連項目

- [データ保持設定を更新する](data-retention-settings.md)
- [アラート通知を構成する](configure-email-notifications.md)
