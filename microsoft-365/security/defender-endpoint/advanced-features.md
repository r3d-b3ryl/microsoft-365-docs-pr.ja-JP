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
ms.openlocfilehash: bcb96ea29649bf3525b2ffcf6d5cbb5d299bacf3
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418118"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Defender for Endpoint で高度な機能を構成する

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

使用する Microsoft セキュリティ製品によっては、Defender for Endpoint を統合できる高度な機能がいくつか用意されている場合があります。

## <a name="enable-advanced-features"></a>高度な機能を有効にする

1. ナビゲーション ウィンドウで、[基本設定]**セットアップの [高度な**  >  **機能] を選択します**。
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


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>スコープ付きデバイス グループ内への相関関係の制限
この設定を有効にすると、アラートはスコープ設定されたデバイス グループに基づいて個別のインシデントに関連付けされます。 既定では、インシデントの相関関係はテナント スコープ全体で発生します。

>[!NOTE]
>この設定を変更すると、将来のアラートの相関関係にのみ影響します。


## <a name="enable-edr-in-block-mode"></a>ブロック モードで EDR を有効にする
ブロック モードのエンドポイント検出と応答 (EDR) は、Microsoft Defender Antivirus がパッシブ モードで実行されている場合でも、悪意のあるアーティファクトからの保護を提供します。 オンにすると、ブロック モードの EDR は、デバイスで検出された悪意のあるアーティファクトや動作をブロックします。 ブロック モードの EDR は、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。

## <a name="autoresolve-remediated-alerts"></a>Autoresolve 修復されたアラート

Windows 10 バージョン 1809 以降に作成されたテナントの場合、自動分析結果の状態が "脅威が見つかりません" または "修復済み" であるアラートを解決するように、自動調査と修復機能が既定で構成されています。  アラートを自動解決したくない場合は、手動で機能をオフにする必要があります。

> [!TIP]
> そのバージョンより前に作成されたテナントの場合は、[高度な機能] ページからこの機能を手動で [有効にする必要](https://securitycenter.windows.com/preferences2/integration) があります。

> [!NOTE]
>
> - 自動解決アクションの結果は、デバイスで検出されたアクティブなアラートに基づくデバイス リスク レベルの計算に影響を与える可能性があります。
> - セキュリティ運用アナリストが手動でアラートの状態を "進行中" または "解決済み" に設定した場合、自動解決機能は上書きされません。

## <a name="allow-or-block-file"></a>ファイルを許可またはブロックする

ブロックは、組織が次の要件を満たしている場合にのみ使用できます。

- アクティブなマルウェア対策ソリューションとして Microsoft Defender ウイルス対策を使用し、
- クラウドベースの保護機能が有効になっている

この機能を使用すると、ネットワーク内の悪意のある可能性のあるファイルをブロックできます。 ファイルをブロックすると、組織内のデバイスでファイルが読み取り、書き込み、または実行されるのを防ぐ。

ファイルを **許可またはブロックするには** 、次の手順を実行します。

1. ナビゲーション ウィンドウで、[設定の詳細設定]**機能**  >  **[ファイルの**  >  **許可またはブロック] を選択します**。

1. [オン] と [オフ]**の間で設定を****切り替えます**。

    ![ブロック ファイル機能の詳細設定のイメージ](images/atp-preferences-setup.png)

1. ページ **の下部にある [基本** 設定の保存] を選択します。

この機能を有効にした後、[](respond-file-alerts.md#allow-or-block-file)ファイルのプロファイルページの [インジケーターの追加] タブを使用してファイルをブロックできます。

## <a name="custom-network-indicators"></a>カスタム ネットワーク インジケーター

この機能を有効にすることで、IP アドレス、ドメイン、または URL のインジケーターを作成し、カスタム インジケーター リストに基づいて許可またはブロックするかどうかを決定できます。

この機能を使用するには、デバイスで Windows 10 バージョン 1709 以降を実行している必要があります。 また、ブロック モードでネットワーク保護を行い、マルウェア対策プラットフォームのバージョン 4.18.1906.3 以降は [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834)を参照してください。

詳細については、「指標の管理 [」を参照してください](manage-indicators.md)。

> [!NOTE]
> ネットワーク保護は、Defender for Endpoint データで選択した場所の外部にある可能性がある場所で要求を処理する評判サービスを活用します。


## <a name="tamper-protection"></a>タンパープロテクション
一部の種類のサイバー攻撃では、悪いアクターがコンピューターでウイルス対策保護などのセキュリティ機能を無効にしようとします。 悪いアクターは、データに簡単にアクセスしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にしています。

タンパープロテクションは基本的に Microsoft Defender ウイルス対策をロックし、アプリやメソッドを通じてセキュリティ設定が変更されるのを防ぐ。

セキュリティ ソリューションとその重要な機能に対する望ましくない変更を防止するために、改ざん防止を有効にしてください。

## <a name="show-user-details"></a>ユーザーの詳細を表示する

この機能を有効にし、Azure Active Directory に格納されているユーザーの詳細を確認できます。 詳細には、ユーザー アカウント エンティティを調査する際のユーザーの画像、名前、タイトル、および部署情報が含まれます。 ユーザー アカウント情報は、次のビューで確認できます。

- セキュリティ運用ダッシュボード
- アラート キュー
- [デバイスの詳細] ページ

詳細については、「ユーザー アカウントの [調査」を参照してください](investigate-user.md)。

## <a name="skype-for-business-integration"></a>Skype for Business 統合

Skype for Business 統合を有効にすると、Skype for Business、電子メール、または電話を使用してユーザーと通信できます。 これは、ユーザーと通信し、リスクを軽減する必要がある場合に便利です。

> [!NOTE]
> デバイスがネットワークから分離されている場合、ユーザーがネットワークから切断されている間にユーザーに通信できる Outlook と Skype の通信を有効にできるポップアップが表示されます。 この設定は、デバイスが分離モードの場合に Skype と Outlook の通信に適用されます。

## <a name="azure-advanced-threat-protection-integration"></a>Azure Advanced Threat Protection の統合

Azure Advanced Threat Protection との統合により、別の Microsoft Identity セキュリティ製品に直接ピボットできます。 Azure Advanced Threat Protection は、侵害された疑いのあるアカウントと関連リソースに関する追加の分析情報を使用して調査を強化します。 この機能を有効にすると、識別の観点からネットワーク全体をピボットすることで、デバイスベースの調査機能を強化できます。

> [!NOTE]
> この機能を有効にするには、適切なライセンスが必要です。

## <a name="office-365-threat-intelligence-connection"></a>Office 365 脅威インテリジェンス接続

この機能は、アクティブな 365 E5 Office脅威インテリジェンス アドオンがある場合にのみ使用できます。 詳細については、「365 Enterprise E5 Office」を参照してください。

この機能を有効にした場合、Office 365 Advanced Threat Protection のデータを Microsoft Defender セキュリティ センターに組み込み、Office 365 メールボックスと Windows デバイス全体で包括的なセキュリティ調査を実行できます。

> [!NOTE]
> この機能を有効にするには、適切なライセンスが必要です。

Office 365 脅威インテリジェンスでコンテキスト デバイスの統合を受け取る場合は、[セキュリティ とコンプライアンス] ダッシュボードで Defender for Endpoint &する必要があります。 詳細については、「脅威の調査 [と対応」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。

## <a name="microsoft-threat-experts"></a>Microsoft 脅威エキスパート

2 つの Microsoft Threat Expert コンポーネントの中で、標的型攻撃通知は一般提供です。 エキスパートオンデマンド機能はまだプレビュー中です。 experts-on-demand 機能は、プレビューを申請し、アプリケーションが承認されている場合にのみ使用できます。 Microsoft Threat Experts から、Defender for Endpoint ポータルのアラート ダッシュボードを介して、および構成した場合は電子メールを介して標的型攻撃通知を受け取ることができます。

> [!NOTE]
> Defender for Endpoint の Microsoft Threat Experts 機能は、エンタープライズ モビリティ + セキュリティの E5 ライセンス [で利用できます](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)。

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

この設定を有効にすると、Defender for Endpoint シグナルが Microsoft Cloud App Security に転送され、クラウド アプリケーションの使用状況を詳細に可視化できます。 転送されたデータは、Cloud App Security データと同じ場所に格納され、処理されます。

> [!NOTE]
> この機能は、Windows 10 バージョン[](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)1709 (OS ビルド 16299.1085 および[KB4493441)](https://support.microsoft.com/help/4493441)、Windows 10 を実行しているデバイスの E5 ライセンスで利用できます。 バージョン 1803 [(KB4493464](https://support.microsoft.com/help/4493464)の OS ビルド 17134.704)、Windows 10 バージョン 1809 (OS ビルド 17763.379 および[KB4489899)](https://support.microsoft.com/help/4489899)以降の Windows 10 バージョン。

## <a name="azure-information-protection"></a>Azure Information Protection

この設定を有効にすると、信号を Azure Information Protection に転送できます。 これにより、データ所有者と管理者は、オンボードデバイス上の保護されたデータとデバイスリスク評価を可視化できます。

## <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

Microsoft Defender for Endpoint シグナルを Microsoft 365 セキュリティ センターの Microsoft Secure Score に転送します。 この機能を有効にすることで、Microsoft Secure Score でデバイスのセキュリティ状態を確認できます。 転送されたデータは、Microsoft Secure Score データと同じ場所に保存および処理されます。

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Microsoft Defender for Identity ポータルから Microsoft Defender for Endpoint の統合を有効にする

Microsoft Defender for Identity でコンテキスト デバイスの統合を受け取る場合は、Microsoft Defender for Identity ポータルで機能を有効にする必要があります。

1. グローバル管理者または [セキュリティ管理者の](https://portal.atp.azure.com/) 役割を持つ Microsoft Defender for Identity ポータルにログインします。

2. [インスタンス **の作成] をクリックします**。

3. [統合] 設定を [オン] **に切り替え、[** 保存] を **クリックします**。

両方のポータルの統合手順を完了すると、デバイスの詳細またはユーザーの詳細ページに関連するアラートを表示できます。

## <a name="microsoft-intune-connection"></a>Microsoft Intune 接続

エンドポイントの Defender を [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) と統合して、デバイスリスクベースの条件付きアクセス [を有効にできます](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。 この機能 [を有効に](configure-conditional-access.md)した場合、Defender for Endpoint デバイス情報を Intune と共有し、ポリシーの適用を強化できます。

> [!IMPORTANT]
> この機能を使用するには、Intune と Defender for Endpoint の両方で統合を有効にする必要があります。 特定の手順の詳細については、「Endpoint 用 [Defender で条件付きアクセスを構成する」を参照してください](configure-conditional-access.md)。

この機能は、次の場合にのみ使用できます。

- エンタープライズ モビリティ + セキュリティ E3、および Windows E5 (または Microsoft 365 Enterprise E5) のライセンステナント
- アクティブな Microsoft Intune 環境で、Intune で管理される Windows 10 デバイス Azure AD [参加しています](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)。

### <a name="conditional-access-policy"></a>条件付きアクセス ポリシー

Intune 統合を有効にした場合、Intune は従来の条件付きアクセス (CA) ポリシーを自動的に作成します。 この従来の CA ポリシーは、Intune に状態レポートを設定する前提条件です。 削除する必要があります。

> [!NOTE]
> Intune によって作成される従来の CA ポリシー[](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)は、エンドポイントの構成に使用される最新の条件付きアクセス ポリシーとは異なります。

## <a name="preview-features"></a>プレビュー機能

Defender for Endpoint プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。

今後の機能にアクセスできます。これは、機能が一般に利用可能になる前に全体的なエクスペリエンスを向上させるためにフィードバックを提供できます。

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Microsoft コンプライアンス センターとエンドポイント通知を共有する

エンドポイント のセキュリティアラートとそのトリアージの状態を Microsoft コンプライアンス センターに転送し、警告を使用してインサイダーリスク管理ポリシーを強化し、内部リスクを害する前に修復することができます。 転送されたデータは、365 データと同じ場所Office保存されます。

Insider リスク管理設定で [セキュリティ ポリシー](/microsoft-365/compliance/insider-risk-management-settings#indicators) 違反インジケーターを構成すると、Defender for Endpoint アラートが該当するユーザーのインサイダー リスク管理と共有されます。

## <a name="related-topics"></a>関連項目

- [データ保持設定の更新](data-retention-settings.md)
- [アラート通知を構成する](configure-email-notifications.md)
