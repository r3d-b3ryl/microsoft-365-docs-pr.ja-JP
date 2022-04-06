---
title: '移行フェーズ 2: セットアップOffice 365 Microsoft Defender に移行する'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: migrationguides
description: サード パーティ製の保護サービスまたはデバイスから Microsoft Defender への移行を開始する手順を実行して、Office 365します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f4f6e1d557915fe40dc570cd58374371e0e9b6a3
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474929"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-2-setup"></a>Microsoft Defender に移行してOffice 365 - フェーズ 2: セットアップ

**適用対象:**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

<br>

|[![フェーズ 1: 準備します。](../../media/phase-diagrams/prepare.png#lightbox)](migrate-to-defender-for-office-365-prepare.md) <br> [フェーズ 1: 準備](migrate-to-defender-for-office-365-prepare.md)|![フェーズ 2: セットアップ。](../../media/phase-diagrams/setup.png) <br> フェーズ 2: 設定|[![フェーズ 3: オンボード。](../../media/phase-diagrams/onboard.png#lightbox)](migrate-to-defender-for-office-365-onboard.md) <br> [フェーズ 3: オンボード](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
||*お前はここにいる!*||

フェーズ **2 へようこそ: Microsoft** **[Defender](migrate-to-defender-for-office-365.md#the-migration-process)** への移行のセットアップをOffice 365! この移行フェーズには、次の手順が含まれます。

1. [パイロット ユーザーの配布グループを作成する](#step-1-create-distribution-groups-for-pilot-users)
2. [ユーザー メッセージレポート用にユーザー申請を構成する](#step-2-configure-user-submission-for-user-message-reporting)
3. [SCL=-1 メール フロー ルールの維持または作成](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)
4. [コネクタの拡張フィルターを構成する](#step-4-configure-enhanced-filtering-for-connectors)
5. [パイロット保護ポリシーの作成](#step-5-create-pilot-protection-policies)

## <a name="step-1-create-distribution-groups-for-pilot-users"></a>手順 1: パイロット ユーザーの配布グループを作成する

移行の次の側面Microsoft 365配布グループが必要です。

- **SCL=-1** メール フロー ルールの例外: パイロット ユーザーが Office 365 保護のために Defender の完全な効果を得る必要があるから、受信メッセージを Defender が Office 365 用にスキャンする必要があります。 これを行うには、Microsoft 365 の適切な配布グループでパイロット ユーザーを定義し、これらのグループを SCL=-1 メール フロー ルールの例外として構成します。

  「Onboard [Step 2: (Optional)](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service) パイロット ユーザーが既存の保護サービスによるフィルター処理を除外する」で説明したように、これらの同じパイロット ユーザーが既存の保護サービスによるスキャンを除外することを検討する必要があります。 既存の保護サービスによるフィルター処理の可能性を排除し、Office 365 の Defender だけに依存する方法は、移行が完了した後に何が起こるかの最も近い表現です。

- **特定の Defender for Office 365保護** 機能のテスト: パイロット ユーザーの場合でも、すべてを一度に有効にしたくはない。 パイロット ユーザーに対して有効な保護機能に対して、ステージ化されたアプローチを使用すると、トラブルシューティングと調整がはるかに簡単になります。 この方法を念頭に置いて、以下の配布グループをお勧めします。
  - **[セーフ添付ファイル] パイロット グループ**: **MDOPilotSafeAttachments\_ など**
  - **[セーフ リンク] パイロット グループ**: **MDOPilotSafeLinks\_ など**
  - **標準のスパム対策** およびフィッシング対策ポリシー設定のパイロット グループ: **たとえば、MDOPilotSpamPhishStandard\_\_**
  - **厳密なスパム対策** およびフィッシング対策ポリシー設定のパイロット グループ: **たとえば、MDOPilotSpamPhishStrict\_\_**

わかりやすくするために、この記事ではこれらの特定のグループ名を使用しますが、独自の名前付け規則を自由に使用できます。

テストを開始する準備ができたら、これらのグループを [例外として SCL=-1 メール フロー ルールに追加します](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)。 Defender for Office 365 のさまざまな保護機能のポリシーを作成する場合、ポリシーが適用されるユーザーを定義する条件としてこれらのグループを使用します。

**注**:

- Standard と Strict という用語は、事前[](recommended-settings-for-eop-and-office365.md)設定されたセキュリティ ポリシーでも使用される推奨されるセキュリティ設定[に基きます](preset-security-policies.md)。 理想的には、標準および厳密な事前設定のセキュリティ ポリシーでパイロット ユーザーを定義する必要がありますが、これを行う必要があります。 どうしてでしょうか? 事前設定されたセキュリティ ポリシー (特に、メッセージに対して実行されるアクション、または偽装保護設定の調整) で設定をカスタマイズできないためです。 移行テスト中に、メッセージに対して Defender for Office 365 が何を行うのかを確認し、それが何を行うのかを確認し、それらの結果を許可または防止するためにポリシー構成を調整する場合があります。

  そのため、事前設定されたセキュリティ ポリシーを使用する代わりに、カスタム ポリシーを手動で作成し、設定と非常に似ていますが、場合によっては Standard と Strict の事前設定セキュリティ ポリシーの設定とは異なる場合があります。

- 標準または厳密な推奨値とは大きく異なる設定を試す場合は、これらのシナリオでパイロット ユーザーに対して追加の配布グループを作成して使用する必要があります。 Configuration Analyzer を使用して、設定のセキュリティ保護を確認できます。 手順については、「EOP の保護ポリシーの構成アナライザー」および「[Microsoft Defender for microsoft Defender for Office 365](configuration-analyzer-for-security-policies.md)。

  ほとんどの組織にとって最善の方法は、推奨される標準設定と密接に一致するポリシーから始める方法です。 利用可能な時間枠で行える限り多くの観察とフィードバックを行った後、後でより積極的な設定に移動できます。 偽装保護と迷惑メール フォルダーへの配信と検疫への配信には、カスタマイズが必要な場合があります。

  カスタマイズしたポリシーを使用する場合は、移行の推奨設定を含むポリシーの前に適用されている必要があります。 ユーザーが同じ種類の複数のポリシー (フィッシング対策など) で識別される場合、その種類のポリシーは 1 つのみ (ポリシーの優先度の値に基づいて) ユーザーに適用されます。 詳細については、「メール保護の [順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="step-2-configure-user-submission-for-user-message-reporting"></a>手順 2: ユーザー メッセージレポートのユーザー申請を構成する

ユーザーが Defender から誤検知または誤検知を識別する機能はOffice 365移行の重要な部分です。

悪意のあるメッセージまたは悪意Exchange Online報告するメッセージを受信するメールボックスを指定できます。 詳細については、「ユーザーが報告した [メッセージ設定」を参照してください](user-submission.md)。 このメールボックスは、ユーザーが Microsoft に送信したメッセージのコピーを受け取る、またはメールボックスがメッセージを Microsoft に報告せずに傍受できます (セキュリティ チームは、手動でメッセージを分析して送信できます)。 ただし、この傍受方法では、サービスが自動的にチューニングおよび学習を行うわけではありません。

また、パイロット内のすべてのユーザーが、ユーザー申請と互換性のあるメッセージ レポート アプリをインストールOutlook確認する必要があります。 これらのアプリには、次のものが含まれます。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)
- [レポートフィッシング アドイン](enable-the-report-phish-add-in.md)
- ここで説明するように、サポートされているサード パーティのレポート [ツール](user-submission.md#third-party-reporting-tools)。

この手順の重要性を過小評価する必要があります。 ユーザー申請からのデータは、移行の前と後に、良好で一貫性のあるエンド ユーザー エクスペリエンスを確認するために必要なフィードバック ループを提供します。 このフィードバックは、情報に基づいたポリシー構成の決定を行うだけでなく、移行がスムーズに行ったというデータベースのレポートを管理に提供するのに役立ちます。

組織全体のエクスペリエンスに裏打ちされたデータに依存する代わりに、複数の移行によって、1 つの否定的なユーザー エクスペリエンスに基づいて感情的な推測が発生しました。 さらに、フィッシング シミュレーションを実行している場合は、ユーザーからのフィードバックを使用して、調査が必要な危険な情報が表示された場合に通知できます。

## <a name="step-3-maintain-or-create-the-scl-1-mail-flow-rule"></a>手順 3: SCL=-1 メール フロー ルールを維持または作成する

受信メールは、Microsoft 365 の前にある別の保護サービスを介してルーティングされます。Exchange Online には、すべての受信メールのスパム信頼レベル (SCL) を値 -1 (バイパス スパム フィルター) に設定するメール フロー ルール (トランスポート ルールとも呼ばれる) が既に存在している可能性が非常に高くなります。 ほとんどのサードパーティの保護サービスでは、サービスを使用するユーザーに対して、この SCL=-1 メール フロー Microsoft 365を推奨しています。

他のメカニズムを使用して Microsoft フィルター スタック (IP 許可リストなど) を上書きする場合は、すべての受信インターネット メールを Microsoft 365 に送信する限り、SCL=-1 メール フロー  ルールの使用に切り替えてください (インターネットから Microsoft 365 への直接メール フローはありません)。

SCL=-1 メール フロー ルールは、次の理由で移行中に重要です。

- Threat Explorer を[使用](email-security-in-microsoft-defender.md)すると、既存の保護サービスの結果に影響を与えることなく、Microsoft スタック内のどの機能がメッセージに作用したのか確認できます。
- SCL=-1 メール フロー ルールの例外を構成することで、Microsoft 365フィルター スタックによって保護されるユーザーを徐々に調整できます。 例外は、この記事の後半で推奨されるパイロット配布グループのメンバーです。

  mx レコードを Microsoft 365 にカットオーバーする前または切り替え中に、このルールを無効にして、組織内のすべての受信者に対する Microsoft 365 保護スタックの完全な保護を有効にします。

詳細については、「メール フロー ルールを使用して、メール フローのメッセージでスパム信頼度 [(SCL) を設定する」を参照](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)Exchange Online。

**注**:

- インターネット メールが既存の保護サービスを通過し、Microsoft 365 に直接同時に流れるのを許可する場合は、SCL=-1 メール フロー ルール (スパム フィルターをバイパスするメール) を、既存の保護サービスを経由したメールにのみ制限する必要があります。 フィルター処理されていないインターネット メールをユーザー のメールボックスに移動Microsoft 365。

  既存の保護サービスによって既にスキャンされているメールを正しく識別するには、SCL=-1 メール フロー ルールに条件を追加できます。 次に例を示します。

  - **クラウドベースの保護サービスの** 場合: 組織に固有のヘッダー値とヘッダー値を使用できます。 ヘッダーを持つメッセージは、ユーザーがスキャンMicrosoft 365。 ヘッダーのないメッセージは、ユーザーがスキャンMicrosoft 365
  - **オンプレミスの保護サービスまたはデバイスの場合**: ソース IP アドレスを使用できます。 送信元 IP アドレスからのメッセージは、ユーザーがスキャンMicrosoft 365。 送信元 IP アドレスからではないメッセージは、ユーザーがスキャンMicrosoft 365。

- メールがフィルター処理されるかどうかを制御するために MX レコードだけに依存しない。 送信者は MX レコードを簡単に無視し、電子メールを直接ユーザーにMicrosoft 365。

## <a name="step-4-configure-enhanced-filtering-for-connectors"></a>手順 4: コネクタの拡張フィルターを構成する

最初に行う必要があるのは、既存の保護サービスから Microsoft 365 へのメール フローに使用されるコネクタの拡張フィルター [処理 (スキップ](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) *リストとも呼* ばれる) を構成します。 受信メッセージ レポート [を使用すると、コネクタ](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports) の識別に役立ちます。

インターネット メッセージが実際にどこから来たのOffice 365を確認するには、Defender がコネクタの拡張フィルター処理を行う必要があります。 強化されたコネクタのフィルター処理により、Microsoft フィルター スタック (特にスプーフィング インテリジェンス、[](anti-spoofing-protection.md)および脅威エクスプローラーと自動調査 [& 応答 (AIR)](automated-investigation-response-office.md) の[](threat-explorer.md)侵害後の機能) の精度が大幅に向上します。

コネクタの拡張フィルターを正しく有効にするには、受信メールを Microsoft 365 にルーティングするすべてのサード パーティ サービスまたはオンプレミスの電子メール システム ホストの **パブリック IP** \***\*\***\* アドレスを追加する必要があります。

コネクタの拡張フィルター処理が機能しているのを確認するには、受信メッセージに次のヘッダーの一方または両方が含まれているか確認します。

- `X-MS-Exchange-SkipListedInternetSender`
- `X-MS-Exchange-ExternalOriginalInternetSender`

## <a name="step-5-create-pilot-protection-policies"></a>手順 5: パイロット保護ポリシーを作成する

実稼働ポリシーを作成すると、すべてのユーザーに適用されていない場合でも、脅威エクスプローラーのような侵害後の機能をテストし[](threat-explorer.md)、セキュリティ応答チームのプロセスに Office 365 用 Defender を統合するテストを行います。

> [!IMPORTANT]
> ポリシーの範囲は、ユーザー、グループ、またはドメインです。 3 つすべてのポリシーに一致するユーザーだけがポリシーの範囲内に入るので、1 つのポリシーで 3 つすべてが混在することをお勧めしません。 パイロット ポリシーの場合は、グループまたはユーザーの使用をお勧めします。 実稼働ポリシーの場合は、ドメインの使用をお勧めします。 ユーザーがポリシーのスコープ内に入るかどうかをユーザーのプライマリ メール ドメインだけが判断する点を理解することが非常に重要です。 そのため、ユーザーのセカンダリ ドメインの MX レコードを切り替える場合は、プライマリ ドメインもポリシーでカバーされます。

### <a name="create-pilot-safe-attachments-policies"></a>パイロット ファイルの添付セーフポリシーを作成する

[セーフ添付ファイルは](safe-attachments.md)、MX レコードを切り替える前Office 365を有効にしてテストするための最も簡単な Defender 機能です。 セーフ添付ファイルには、次の利点があります。

- 最小限の構成。
- 誤検知の可能性が非常に低い。
- マルウェア対策保護と同様の動作。これは常にオンであり、SCL=-1 メール フロー ルールの影響を受けずに行います。

パイロット ユーザーセーフ添付ファイル ポリシーを作成します。

推奨される設定については、「添付ファイルの[推奨設定セーフ」を参照してください](recommended-settings-for-eop-and-office365.md#safe-attachments-policy-settings)。 Standard と Strict の推奨事項は同じに注意してください。 ポリシーを作成するには、「添付ファイル ポリシー[のセーフ」を参照してください](set-up-safe-attachments-policies.md)。 ポリシーの条件として **グループ MDOPilotSafeAttachments\_** を使用してください (ポリシーが適用されるユーザー)。

> [!IMPORTANT]
> 現在、添付ファイル ポリシーの既定セーフはありません。 MX レコードを切り替える前に、組織全体を保護セーフ添付ファイル ポリシーを使用することをお勧めします。

### <a name="create-pilot-safe-links-policies"></a>パイロット リンク ポリシーセーフ作成する

> [!NOTE]
> 既にラップまたは書き換え済みのリンクの折り返しや書き換えはサポートされていません。 現在の保護サービスで電子メール メッセージ内のリンクが既にラップまたは書き換えされている場合は、パイロット ユーザーに対してこの機能をオフにする必要があります。 この問題が発生しない方法の 1 つは、[リンク] ポリシーで他のサービスの URL ドメインをセーフです。
>
> セーフサポートされているアプリOfficeリンク保護は、すべてのライセンスユーザーに適用されるグローバル設定です。 特定のユーザーではなく、グローバルに有効またはオフにできます。 詳細については、「Configure [セーフ リンク保護 for Office 365」を参照してください](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal)。

パイロット ユーザーセーフリンク ポリシーを作成します。 セーフ リンクの誤検知の可能性もかなり低いですが、添付ファイルよりも少ない数のパイロット ユーザーでこの機能をテストセーフ必要があります。 この機能はユーザー エクスペリエンスに影響を与えるので、ユーザーを教育する計画を検討する必要があります。

推奨される設定については、「推奨されるリンク[ポリシーセーフ」を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-settings)。 Standard と Strict の推奨事項は同じに注意してください。 ポリシーを作成するには、「リンク ポリシーの[セーフ」を参照してください](set-up-safe-links-policies.md)。 ポリシーの条件として **グループ MDOPilotSafeLinks\_** を使用してください (ポリシーが適用されるユーザー)。

> [!IMPORTANT]
> 現在、既定のリンク ポリシーセーフはありません。 MX レコードを切り替える前に、組織全体を保護セーフリンク ポリシーを使用することをお勧めします。

### <a name="create-pilot-anti-spam-policies"></a>パイロットスパム対策ポリシーの作成

パイロット ユーザーに対して 2 つのスパム対策ポリシーを作成します。

- 標準設定を使用するポリシー。 ポリシーの **条件としてグループ MDOPilotSpamPhishStandard\_\_** を使用します (ポリシーが適用されるユーザー)。
- 厳密な設定を使用するポリシー。 ポリシーの条件 **としてグループ MDOPilotSpamPhishStrict\_\_** を使用します (ポリシーが適用されるユーザー)。 このポリシーは、標準設定のポリシーよりも優先度が高い (数値が低い) 必要があります。

推奨される標準と厳密な設定については、「推奨されるスパム対策 [ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。 ポリシーを作成するには、「スパム対策ポリシー [を構成する」を参照してください](configure-your-spam-filter-policies.md)。

### <a name="create-pilot-anti-phishing-policies"></a>パイロットフィッシング対策ポリシーの作成

パイロット ユーザーに対して 2 つのフィッシング対策ポリシーを作成します。

- 以下で説明する偽装検出アクションを除き、標準設定を使用するポリシー。 ポリシーの **条件としてグループ MDOPilotSpamPhishStandard\_\_** を使用します (ポリシーが適用されるユーザー)。
- 以下で説明する偽装検出アクションを除き、厳密な設定を使用するポリシー。 ポリシーの条件 **としてグループ MDOPilotSpamPhishStrict\_\_** を使用します (ポリシーが適用されるユーザー)。 このポリシーは、標準設定のポリシーよりも優先度が高い (数値が低い) 必要があります。

スプーフィング検出の場合、推奨される標準アクションは[メッセージを受信者の迷惑メール フォルダーに移動する] で、推奨される Strict アクションは [メッセージ **の検疫] です**。 スプーフィング インテリジェンスの分析情報を使用して結果を確認します。 オーバーライドについては、次のセクションで説明します。 詳細については、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。

偽装の検出では、パイロット ポリシーに推奨される Standard アクションと Strict アクションは無視してください。 代わりに、次の設定に対 **してアクションを適用しないという** 値を使用します。

- **偽装ユーザーとしてメッセージが検出された場合**
- **偽装ドメインとしてメッセージが検出された場合**
- **メールボックス インテリジェンスが偽装ユーザーを検出した場合**

偽装インサイトを使用して結果を確認します。 詳細については、「Defender for [Office 365」を参照してください](impersonation-insight.md)。

スプーフィング保護 (許可とブロックの調整) を調整し、各偽装保護アクションを有効にし、メッセージを検疫または迷惑メール フォルダー (標準または厳密な推奨事項に基づく) に移動します。 結果を確認し、必要に応じて設定を調整できます。

詳細については、次のトピックをご覧ください。

- [スプーフィング対策保護](anti-spoofing-protection.md)
- [フィッシング対策ポリシーの偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Defender でフィッシング対策ポリシーを構成して、](configure-mdo-anti-phishing-policies.md)Office 365。

## <a name="next-step"></a>次の手順

**おめでとう** ございます! Microsoft Defender への移行の **セットアップ** フェーズを完了し [、](migrate-to-defender-for-office-365.md#the-migration-process)Office 365!

- フェーズ [3: オンボードに進みます](migrate-to-defender-for-office-365-onboard.md)。
