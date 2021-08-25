---
title: Microsoft Defender for Endpoint の高度な機能を構成する
description: Microsoft Defender for Endpoint のブロック ファイルなどの高度な機能を有効にする。
keywords: 高度な機能、設定、ファイルのブロック、自動調査、自動解決、skype、id の microsoft Defender、Office 365、Azure 情報保護、intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bd56ab7daef91fb06aca8bc9d60213877b9696b8
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58507760"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Defender for Endpoint で高度な機能を構成する

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedfeats-abovefoldlink)

使用する Microsoft セキュリティ製品によっては、Defender for Endpoint を統合できる高度な機能がいくつか用意されている場合があります。

## <a name="enable-advanced-features"></a>高度な機能を有効にする

1. ナビゲーション ウィンドウで、[エンドポイントの詳細設定 **] 設定** \> **を** \> **選択します**。
2. 構成する高度な機能を選択し、設定を [オン] と [オフ] **の間で切り** 替 **えます**。
3. [設定 **の保存] をクリックします**。

次の高度な機能を使用して、潜在的に悪意のあるファイルから保護され、セキュリティ調査中により良い洞察を得る。

## <a name="automated-investigation"></a>自動調査

この機能を有効にし、サービスの自動調査および修復機能を利用します。 詳細については、「自動調査 [」を参照してください](automated-investigations.md)。

## <a name="live-response"></a>ライブ応答

適切なアクセス許可を持つユーザーがデバイスでライブ応答セッションを開始できるよう、この機能を有効にします。

役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。

## <a name="live-response-for-servers"></a>サーバーのライブ応答

この機能を有効にし、適切なアクセス許可を持つユーザーがサーバーでライブ応答セッションを開始できます。

役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。

## <a name="live-response-unsigned-script-execution"></a>ライブ応答の署名されていないスクリプトの実行

この機能を有効にすると、ライブ応答セッションで署名されていないスクリプトを実行できます。

## <a name="always-remediate-pua"></a>PUA を常に修復する

望ましくない可能性のあるアプリケーション (PUA) は、コンピューターの動作が遅くなる、予期しない広告を表示する、または最悪の場合は他のソフトウェアをインストールするソフトウェアのカテゴリです。予期しない、または望ましくない可能性があります。

この機能を有効にし、PUA 保護がデバイスで構成されていない場合でも、不要な可能性のあるアプリケーション (PUA) がテナント内のすべてのデバイスで修復されます。 これにより、ユーザーがデバイスに不要なアプリケーションを誤ってインストールすることを防役立ちます。 オフにすると、修復はデバイスの構成に依存します。

## <a name="restrict-correlation-to-within-scoped-device-groups"></a>スコープ付きデバイス グループ内への相関関係の制限

この構成は、ローカルの SOC 操作でアラートの相関関係をアクセスできるデバイス グループにのみ制限する場合に使用できます。 この設定を有効にすると、デバイス グループをまたがったアラートで構成されるインシデントは、1 つのインシデントとは見なされません。 ローカル SOC は、関連するデバイス グループの 1 つへのアクセス権を持つため、インシデントに対してアクションを実行できます。 ただし、グローバル SOC では、1 つのインシデントではなく、デバイス グループ別に複数の異なるインシデントが表示されます。 組織全体のインシデントの相関関係の利点を上回らない限り、この設定を有効にすることをお勧めしません。

> [!NOTE]
> この設定を変更すると、将来のアラートの相関関係にのみ影響します。

## <a name="enable-edr-in-block-mode"></a>ブロック モードEDR有効にする

ブロック モードでのエンドポイントの検出と応答 (EDR) は、パッシブ モードで実行されている場合でも、悪意のあるMicrosoft Defender ウイルス対策からの保護を提供します。 オンにすると、EDRモードでデバイスで検出された悪意のあるアーティファクトや動作がブロックされます。 EDRモードでは、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。

## <a name="autoresolve-remediated-alerts"></a>Autoresolve 修復されたアラート

Windows 10 Version 1809 以降に作成されたテナントの場合、自動調査および修復機能は既定で構成され、自動分析結果の状態が "脅威が見つかりません" または "修復済み" であるアラートを解決します。 アラートを自動解決したくない場合は、手動で機能をオフにする必要があります。

> [!TIP]
> そのバージョンより前に作成されたテナントの場合は、[高度な機能] ページからこの機能を手動で [有効にする必要](https://security.microsoft.com//preferences2/integration) があります。

> [!NOTE]
>
> - 自動解決アクションの結果は、デバイスで検出されたアクティブなアラートに基づくデバイス リスク レベルの計算に影響を与える可能性があります。
> - セキュリティ運用アナリストが手動でアラートの状態を "進行中" または "解決済み" に設定した場合、自動解決機能は上書きされません。

## <a name="allow-or-block-file"></a>ファイルを許可またはブロックする

ブロックは、組織が次の要件を満たしている場合にのみ使用できます。

- アクティブMicrosoft Defender ウイルス対策マルウェア対策ソリューションとして使用し、
- クラウドベースの保護機能が有効になっている

この機能を使用すると、ネットワーク内の悪意のある可能性のあるファイルをブロックできます。 ファイルをブロックすると、組織内のデバイスでファイルが読み取り、書き込み、または実行されるのを防ぐ。

ファイルを **許可またはブロックするには** 、次の手順を実行します。

1. ナビゲーション ウィンドウで、[エンドポイントの全般 **詳細設定設定** ファイルを許可またはブロック \>  \>  \>  \> **する] を選択します**。

1. [オン] と [オフ]**の間で設定を****切り替えます**。

    :::image type="content" source="../../media/alloworblockfile.png" alt-text="ブロック ファイル機能の詳細設定のイメージ":::

1. ページ **の下部にある [基本** 設定の保存] を選択します。

この機能を有効にした後、[](respond-file-alerts.md#allow-or-block-file)ファイルのプロファイルページの [インジケーターの追加] タブを使用してファイルをブロックできます。

## <a name="custom-network-indicators"></a>カスタム ネットワーク インジケーター

この機能を有効にすることで、IP アドレス、ドメイン、または URL のインジケーターを作成し、カスタム インジケーター リストに基づいて許可またはブロックするかどうかを決定できます。

この機能を使用するには、デバイスがバージョン 1709 以降Windows 10実行している必要があります。 また、ブロック モードでネットワーク保護を行い、マルウェア対策プラットフォームのバージョン 4.18.1906.3 以降は KB 4052623 を参照 [してください](https://go.microsoft.com/fwlink/?linkid=2099834)。

詳細については、「指標の管理 [」を参照してください](manage-indicators.md)。

> [!NOTE]
> ネットワーク保護は、Defender for Endpoint データで選択した場所の外部にある可能性がある場所で要求を処理する評判サービスを活用します。

## <a name="tamper-protection"></a>タンパープロテクション
一部の種類のサイバー攻撃では、悪いアクターがコンピューターでウイルス対策保護などのセキュリティ機能を無効にしようとします。 悪いアクターは、データに簡単にアクセスしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にしています。

タンパープロテクションは基本的Microsoft Defender ウイルス対策ロックし、アプリやメソッドを通じてセキュリティ設定が変更されるのを防ぐ。

この機能は、組織でクラウド ベースMicrosoft Defender ウイルス対策が有効になっている場合に使用できます。 詳細については、「クラウドで提供される保護を通じて、Microsoft Defender ウイルス対策テクノロジを使用[する」を参照してください](cloud-protection-microsoft-defender-antivirus.md)。

セキュリティ ソリューションとその重要な機能に対する望ましくない変更を防止するために、改ざん防止を有効にしてください。

## <a name="show-user-details"></a>ユーザーの詳細を表示する

この機能を有効にし、ユーザーの詳細がユーザーの詳細を表示Azure Active Directory。 詳細には、ユーザー アカウント エンティティを調査する際のユーザーの画像、名前、タイトル、および部署情報が含まれます。 ユーザー アカウント情報は、次のビューで確認できます。

- セキュリティ運用ダッシュボード
- アラート キュー
- [デバイスの詳細] ページ

詳細については、「ユーザー アカウントの [調査」を参照してください](investigate-user.md)。

## <a name="skype-for-business-integration"></a>Skype for Business 統合

この統合をSkype for Businessすることで、ユーザーとのコミュニケーションをSkype for Business、電子メール、または電話を使用できます。 これは、ユーザーと通信し、リスクを軽減する必要がある場合に便利です。

> [!NOTE]
> デバイスがネットワークから分離されている場合は、Outlook および Skype 通信を有効にし、ネットワークから切断されている間にユーザーに通信できるポップアップが表示されます。 この設定は、デバイスがSkypeモードOutlook通信に適用されます。

## <a name="microsoft-defender-for-identity-integration"></a>Id 統合用 Microsoft Defender

Microsoft Defender for Identity との統合により、別の Microsoft Identity セキュリティ製品に直接ピボットできます。 Microsoft Defender for Identity は、侵害された疑いのあるアカウントと関連リソースに関するより多くの洞察を得て調査を強化します。 この機能を有効にすると、識別の観点からネットワーク全体をピボットすることで、デバイスベースの調査機能を強化できます。

> [!NOTE]
> この機能を有効にするには、適切なライセンスが必要です。

## <a name="office-365-threat-intelligence-connection"></a>Office 365脅威インテリジェンス接続

この機能は、アクティブなユーザーまたは脅威インテリジェンス Office 365 E5を使用している場合にのみ使用できます。 詳細については、「E5 製品のOffice 365 Enterpriseを参照してください。

この機能を有効にした場合、microsoft Defender for Office 365 のデータを Microsoft 365 Defender に組み込み、Office 365 メールボックスと Windows デバイス全体で包括的なセキュリティ調査を実行できます。

> [!NOTE]
> この機能を有効にするには、適切なライセンスが必要です。

脅威インテリジェンスでコンテキスト デバイスのOffice 365を受け取る場合は、[セキュリティ とコンプライアンス] ダッシュボードで Defender for Endpoint &する必要があります。 詳細については、「脅威の調査 [と対応」を参照してください](/microsoft-365/security/office-365-security/office-365-ti)。

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft 脅威エキスパート - ターゲット攻撃通知

2 つの Microsoft Threat Expert コンポーネントの中で、標的型攻撃通知は一般提供です。 エキスパートオンデマンド機能はまだプレビュー中です。 experts-on-demand 機能は、プレビューを申請し、アプリケーションが承認されている場合にのみ使用できます。 ターゲット攻撃通知は、Defender for Endpoint ポータルMicrosoft 脅威エキスパート、構成した場合は電子メールを介して、ターゲット攻撃通知を受信できます。

> [!NOTE]
> Defender for Endpoint Microsoft 脅威エキスパートの機能は、エンドポイントの E5 ライセンスで[Enterprise Mobility + Security。](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

この設定を有効にすると、Defender for Endpoint シグナルMicrosoft Cloud App Securityに転送され、クラウド アプリケーションの使用状況を詳細に確認できます。 転送されたデータは、ユーザーのデータと同じ場所にCloud App Securityされます。

> [!NOTE]
> この機能は、E5 ライセンスを使用して[、Enterprise Mobility + Securityを実行](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)しているWindows 10 バージョン 1709 [(KB4493441](https://support.microsoft.com/help/4493441)の OS ビルド 16299.1085)、Windows 10 バージョン 1803 (OS ビルド 17134.704 [KB449364)、Windows 10 Version 1809](https://support.microsoft.com/help/4493464)(OS ビルド 17763.379 および[KB4489899)、](https://support.microsoft.com/help/4489899)または Windows 10 以降のバージョン。

## <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

Microsoft Defender for Endpoint シグナルをセキュリティ センターの Microsoft Secure Score に転送Microsoft 365します。 この機能を有効にすることで、Microsoft Secure Score でデバイスのセキュリティ状態を確認できます。 転送されたデータは、Microsoft Secure Score データと同じ場所に保存および処理されます。

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Microsoft Defender for Identity ポータルから Microsoft Defender for Endpoint の統合を有効にする

Microsoft Defender for Identity でコンテキスト デバイスの統合を受け取る場合は、Microsoft Defender for Identity ポータルで機能を有効にする必要があります。

1. グローバル管理者または [セキュリティ管理者の](https://portal.atp.azure.com/) 役割を持つ Microsoft Defender for Identity ポータルにログインします。

2. [インスタンス **の作成] をクリックします**。

3. [統合] 設定を [オン] **に切り替え、[** 保存] を **クリックします**。

両方のポータルの統合手順を完了すると、デバイスの詳細またはユーザーの詳細ページに関連するアラートを表示できます。

## <a name="web-content-filtering"></a>Web コンテンツ フィルタリング

望ましくないコンテンツを含む Web サイトへのアクセスをブロックし、すべてのドメインで Web アクティビティを追跡します。 ブロックする Web コンテンツ カテゴリを指定するには、Web コンテンツ フィルター ポリシー [を作成します](https://security.microsoft.com/preferences2/web_content_filtering_policy)。 Microsoft Defender for Endpoint セキュリティ ベースラインを展開する場合は、ブロック モードでネットワーク保護 [を行う必要があります](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)。


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Microsoft コンプライアンス センターとエンドポイント通知を共有する

エンドポイント のセキュリティアラートとそのトリアージの状態を Microsoft コンプライアンス センターに転送し、警告を使用してインサイダーリスク管理ポリシーを強化し、内部リスクを害する前に修復することができます。 転送されたデータは、ユーザーのデータと同じ場所にOffice 365されます。

Insider リスク管理設定で [セキュリティ ポリシー](/microsoft-365/compliance/insider-risk-management-settings#indicators) 違反インジケーターを構成すると、Defender for Endpoint アラートが該当するユーザーのインサイダー リスク管理と共有されます。

## <a name="microsoft-intune-connection"></a>Microsoft Intune接続

Defender for Endpoint は、デバイス リスクベースの条件付[Microsoft Intune](/intune/what-is-intune)[アクセスを有効にするアプリケーションと統合できます](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。 この機能 [を有効に](configure-conditional-access.md)した場合、Defender for Endpoint デバイス情報を Intune と共有し、ポリシーの適用を強化できます。

> [!IMPORTANT]
> この機能を使用するには、Intune と Defender for Endpoint の両方で統合を有効にする必要があります。 特定の手順の詳細については、「Endpoint 用 [Defender で条件付きアクセスを構成する」を参照してください](configure-conditional-access.md)。

この機能は、次の場合にのみ使用できます。

- E5 (または E5) Enterprise Mobility + Security E3およびWindowsライセンスMicrosoft 365 Enterpriseテナント
- アクティブなMicrosoft Intune環境で、Intune が管理するデバイスWindows 10 Azure AD[参加しています](/azure/active-directory/devices/concept-azure-ad-join/)。

### <a name="conditional-access-policy"></a>条件付きアクセス ポリシー

Intune 統合を有効にした場合、Intune は従来の条件付きアクセス (CA) ポリシーを自動的に作成します。 この従来の CA ポリシーは、Intune に状態レポートを設定する前提条件です。 削除する必要があります。

> [!NOTE]
> Intune によって作成される従来の CA ポリシー[](/azure/active-directory/conditional-access/overview/)は、エンドポイントの構成に使用される最新の条件付きアクセス ポリシーとは異なります。

## <a name="device-discovery"></a>デバイス検出

追加のアプライアンスや面倒なプロセス変更を必要とせずに、企業ネットワークに接続されている管理されていないデバイスを見つけるのに役立ちます。 オンボード デバイスを使用すると、ネットワーク内の管理されていないデバイスを見つけて、脆弱性とリスクを評価できます。 詳細については、「デバイスの検出 [」を参照してください](device-discovery.md)。

> [!NOTE]
> フィルターをいつでも適用して、デバイス インベントリ リストから管理されていないデバイスを除外できます。 また、API クエリのオンボーディング状態列を使用して、管理されていないデバイスをフィルター処理することもできます。

## <a name="preview-features"></a>プレビュー機能

Defender for Endpoint プレビュー リリースの新機能について説明します。 プレビュー エクスペリエンスをオンにして、今後の機能を試してみてください。

今後の機能にアクセスできます。これは、機能が一般に利用可能になる前に全体的なエクスペリエンスを向上させるためにフィードバックを提供できます。

## <a name="download-quarantined-files"></a>検疫済みファイルのダウンロード

検疫済みファイルを安全で準拠した場所にバックアップし、検疫から直接ダウンロードできます。 [ **ファイルのダウンロード]** ボタンは常にファイル ページで使用できます。 この設定は既定でオンになっています。 [要件の詳細](respond-file-alerts.md#download-quarantined-files)

## <a name="related-topics"></a>関連項目

- [データ保持設定の更新](data-retention-settings.md)
- [アラート通知を構成する](configure-email-notifications.md)
