---
title: 'Microsoft Defender for Office 365 フェーズ 2: セットアップに移行する'
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
- m365solution-mdo-migration
ms.custom: migrationguides
description: サード パーティの保護サービスまたはデバイスからMicrosoft Defender for Office 365保護への移行を開始する手順を実行します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 69af51bbd39339b07af8f0832a113184afaf725b
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051692"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-2-setup"></a>Microsoft Defender for Office 365に移行する - フェーズ 2: セットアップ

**適用対象:**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

<br>

|[![フェーズ 1: 準備します。](../../media/phase-diagrams/prepare.png#lightbox)](migrate-to-defender-for-office-365-prepare.md) <br> [フェーズ 1: 準備](migrate-to-defender-for-office-365-prepare.md)|![フェーズ 2: セットアップします。](../../media/phase-diagrams/setup.png) <br> フェーズ 2: 設定|[![フェーズ 3: オンボード。](../../media/phase-diagrams/onboard.png#lightbox)](migrate-to-defender-for-office-365-onboard.md) <br> [フェーズ 3: オンボード](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
||*お客様はここにいます。*||

**フェーズ 2 へようこそ:****[Microsoft Defender for Office 365への移行](migrate-to-defender-for-office-365.md#the-migration-process)** のセットアップ! この移行フェーズには、次の手順が含まれます。

1. [パイロット ユーザーの配布グループを作成する](#step-1-create-distribution-groups-for-pilot-users)
2. [ユーザー メッセージ レポートのユーザー送信を構成する](#step-2-configure-user-submission-for-user-message-reporting)
3. [SCL=-1 メール フロー ルールを維持または作成する](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)
4. [コネクタの拡張フィルター処理を構成する](#step-4-configure-enhanced-filtering-for-connectors)
5. [パイロット保護ポリシーを作成する](#step-5-create-pilot-protection-policies)

## <a name="step-1-create-distribution-groups-for-pilot-users"></a>手順 1: パイロット ユーザーの配布グループを作成する

移行の次の側面については、Microsoft 365 で配布グループが必要です。

- **SCL=-1 メール フロー ルールの例外**: パイロット ユーザーがDefender for Office 365保護の完全な効果を得られるようにするには、受信メッセージをDefender for Office 365によってスキャンする必要があります。 これを行うには、Microsoft 365 の適切な配布グループにパイロット ユーザーを定義し、これらのグループを SCL=-1 メール フロー ルールの例外として構成します。

  [オンボード手順 2: (省略可能) パイロット ユーザーが既存の保護サービスによるフィルター処理を](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)除外する」で説明したように、これらの同じパイロット ユーザーが既存の保護サービスによるスキャンを除外することを検討する必要があります。 既存の保護サービスでフィルター処理を行い、Defender for Office 365のみに依存する可能性を排除することは、移行が完了した後に何が起こるかを最も近く表現することです。

- **特定のDefender for Office 365保護機能のテスト**: パイロット ユーザーであっても、すべてを一度に有効にしたくありません。 パイロット ユーザーに対して有効な保護機能に段階的なアプローチを使用すると、トラブルシューティングと調整がはるかに簡単になります。 この方法を念頭に置いて、次の配布グループをお勧めします。
  - **安全な添付ファイルパイロット グループ**: たとえば、 **MDOPilot\_SafeAttachments**
  - **安全なリンクのパイロット グループ**: たとえば、 **MDOPilot\_SafeLinks**
  - **標準スパム対策とフィッシング対策ポリシー設定のパイロット グループ**: たとえば、 **MDOPilot\_SpamPhish\_Standard**
  - **厳格なスパム対策とフィッシング対策ポリシー設定のパイロット グループ**: たとえば、 **MDOPilot\_SpamPhish\_Strict**

わかりやすくするために、この記事全体でこれらの特定のグループ名を使用しますが、独自の名前付け規則を自由に使用できます。

テストを開始する準備ができたら、これらのグループを例外として [SCL=-1 メール フロー ルール](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)に追加します。 Defender for Office 365のさまざまな保護機能のポリシーを作成するときに、ポリシーが適用されるユーザーを定義する条件としてこれらのグループを使用します。

**注意**:

- Standard および Strict という用語は、 [推奨されるセキュリティ設定](recommended-settings-for-eop-and-office365.md)に由来します。これは、 [事前設定されたセキュリティ ポリシー](preset-security-policies.md)でも使用されます。 理想的には、Standard および Strict の事前設定済みセキュリティ ポリシーでパイロット ユーザーを定義することをお勧めしますが、これを行うことはできません。 どうしてでしょうか? 事前設定されたセキュリティ ポリシー (特に、メッセージに対して実行されるアクション) の設定をカスタマイズできないためです。 移行テスト中に、メッセージに対して実行するDefender for Office 365を確認し、それが何を行うかを確認し、それらの結果を許可または防止するようにポリシー構成を調整する必要があります。

  そのため、事前設定されたセキュリティ ポリシーを使用する代わりに、非常に似た設定でカスタム ポリシーを手動で作成しますが、場合によっては、Standard および Strict の事前設定のセキュリティ ポリシーの設定とは異なります。

- Standard または Strict の推奨値と **大きく** 異なる設定を試す場合は、これらのシナリオでパイロット ユーザーに対して追加の配布グループと特定の配布グループを作成して使用することを検討する必要があります。 Configuration Analyzer を使用して、設定の安全性を確認できます。 手順については、[EOP およびMicrosoft Defender for Office 365の保護ポリシーの構成アナライザーに関する](configuration-analyzer-for-security-policies.md)記事を参照してください。

  ほとんどの組織では、推奨される標準設定と密接に一致するポリシーから始めるのが最善の方法です。 使用可能な時間枠で実行できる限り多くの観察とフィードバックを得た後は、後でより積極的な設定に移動できます。 偽装の保護と迷惑メール Email フォルダーへの配信と検疫への配信にはカスタマイズが必要な場合があります。

  カスタマイズされたポリシーを使用する場合は、移行に推奨される設定が含まれているポリシーの _前に_ 適用されていることを確認してください。 ユーザーが同じ種類の複数のポリシー (フィッシング対策など) で識別された場合、その種類のポリシーは 1 つだけ (ポリシーの優先度値に基づいて) ユーザーに適用されます。 詳細については、「[メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

## <a name="step-2-configure-user-submission-for-user-message-reporting"></a>手順 2: ユーザー メッセージ レポートのユーザー送信を構成する

ユーザーがDefender for Office 365から誤検知または偽陰性を識別する機能は、移行の重要な部分です。

Exchange Online メールボックスを指定して、ユーザーが悪意のある、または悪意のないメッセージとして報告するメッセージを受信できます。 詳細については、「 [ユーザーが報告したメッセージ設定](user-submission.md)」を参照してください。 このメールボックスは、ユーザーが Microsoft に送信したメッセージのコピーを受け取ることができます。または、メールボックスは Microsoft に報告せずにメッセージを傍受できます (セキュリティ チームは、メッセージを手動で分析して送信できます)。 ただし、このインターセプト アプローチでは、サービスが自動的に調整および学習することはできません。

また、パイロットのすべてのユーザーが、Outlook にインストールされているサポートされているメッセージ レポート アプリをユーザー提出と互換性があることを確認する必要があります。 これらのアプリには、次のものが含まれます。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)
- [レポート フィッシング アドイン](enable-the-report-phish-add-in.md)
- [ここで](user-submission.md#third-party-reporting-tools-options)説明するように、サポートされているサード パーティのレポート ツール。

この手順の重要性を過小評価しないでください。 ユーザー提出のデータにより、移行前と移行後に良好で一貫性のあるエンド ユーザー エクスペリエンスを確認するために必要なフィードバック ループが提供されます。 このフィードバックは、情報に基づいたポリシー構成の決定を行うだけでなく、移行がスムーズに進んだというデータに基づくレポートを管理に提供するのに役立ちます。

組織全体の経験に裏打ちされたデータに依存する代わりに、1 つの負のユーザー エクスペリエンスに基づいて、複数の移行によって感情投機が生まれています。 さらに、フィッシング シミュレーションを実行している場合は、ユーザーからのフィードバックを使用して、調査が必要になる可能性のある危険な情報をユーザーに通知できます。

## <a name="step-3-maintain-or-create-the-scl-1-mail-flow-rule"></a>手順 3: SCL=-1 メール フロー ルールを維持または作成する

受信メールは Microsoft 365 の前にある別の保護サービスを介してルーティングされるため、すべての受信メールのスパム信頼レベル (SCL) を値 -1 (スパム フィルターをバイパス) に設定する Exchange Onlineメール フロー ルール (トランスポート ルールとも呼ばれます) が既にある可能性が高くなります。 ほとんどのサード パーティの保護サービスでは、サービスを使用する Microsoft 365 のお客様に対して、この SCL=-1 メール フロー ルールを推奨しています。

Microsoft フィルター スタック (IP 許可リストなど) をオーバーライドするために他のメカニズムを使用している場合は、Microsoft 365 への受信インターネット メールがすべてサード パーティの保護サービスから送信されている (インターネットから Microsoft 365 に直接メールが流れていない) **限り** 、SCL=-1 メール フロー ルールの使用に切り替えることをお勧めします。

SCL=-1 メール フロー ルールは、次の理由から移行中に重要です。

- [脅威エクスプローラー](email-security-in-microsoft-defender.md)を使用すると、既存の保護サービスの結果に影響を与えずに、*Microsoft スタックのどの* 機能がメッセージに対して動作したかを確認できます。
- SCL=-1 メール フロー ルールに対する例外を構成することで、Microsoft 365 フィルター スタックによって保護されているユーザーを徐々に調整できます。 例外は、この記事の後半で推奨されるパイロット配布グループのメンバーです。

  MX レコードを Microsoft 365 に切り替える前または間に、このルールを無効にして、組織内のすべての受信者に対して Microsoft 365 保護スタックの完全な保護を有効にします。

詳細については、「[メール フロー ルールを使用して、Exchange Online内のメッセージでスパム信頼レベル (SCL) を設定](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)する」を参照してください。

**注意**:

- インターネット メールが既存の保護サービスを経由 **し、** 同時に Microsoft 365 に直接送信されるようにする場合は、SCL=-1 メール フロー ルール (スパム フィルターをバイパスするメール) を、既存の保護サービスのみを通過するメールに制限する必要があります。 Microsoft 365 のユーザー メールボックスにフィルター処理されていないインターネット メールのランディングは必要ありません。

  既存の保護サービスによって既にスキャンされているメールを正しく識別するには、SCL=-1 メール フロー ルールに条件を追加します。 以下に例を示します。

  - **クラウドベースの保護サービスの場合**: 組織に固有のヘッダーとヘッダーの値を使用できます。 ヘッダーを含むメッセージは、Microsoft 365 によってスキャンされません。 ヘッダーのないメッセージは、Microsoft 365 によってスキャンされます
  - **オンプレミスの保護サービスまたはデバイスの** 場合: ソース IP アドレスを使用できます。 ソース IP アドレスからのメッセージは、Microsoft 365 によってスキャンされません。 ソース IP アドレスからではないメッセージは、Microsoft 365 によってスキャンされます。

- メールがフィルター処理されるかどうかを制御するために、MX レコードのみに依存しないでください。 送信者は MX レコードを簡単に無視し、Microsoft 365 に直接メールを送信できます。

## <a name="step-4-configure-enhanced-filtering-for-connectors"></a>手順 4: コネクタの拡張フィルター処理を構成する

最初に行うには、既存の保護サービスから Microsoft 365 へのメール フローに使用されるコネクタの [拡張フィルター処理](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ( *リストのスキップ* とも呼ばれます) を構成します。 [受信メッセージ レポート](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports)を使用すると、コネクタの識別に役立ちます。

コネクタの強化されたフィルター処理は、インターネット メッセージが実際にどこから来たのかを確認するためにDefender for Office 365で必要です。 コネクタのフィルター処理の強化により、Microsoft フィルター スタックの精度が大幅に向上します (特に、ス [プーフィング インテリジェンス](anti-spoofing-protection.md)、 [脅威エクスプローラー](threat-explorer.md) と [自動調査&応答 (AIR) の](automated-investigation-response-office.md)違反後の機能)。

コネクタの拡張フィルター処理を正しく有効にするには、受信メールを Microsoft 365 にルーティング **するすべての\*\*** サード パーティサービスまたはオンプレミスの電子メール システム ホストの **パブリック** IP アドレス\*\*を追加する必要があります。

コネクタの拡張フィルター処理が機能していることを確認するには、受信メッセージに次のヘッダーのいずれかまたは両方が含まれていることを確認します。

- `X-MS-Exchange-SkipListedInternetSender`
- `X-MS-Exchange-ExternalOriginalInternetSender`

## <a name="step-5-create-pilot-protection-policies"></a>手順 5: パイロット保護ポリシーを作成する

運用ポリシーを作成することで、すべてのユーザーに適用されていない場合でも、[脅威エクスプローラー](threat-explorer.md)などの違反後の機能をテストし、セキュリティ対応チームのプロセスにDefender for Office 365を統合するテストを行うことができます。

> [!IMPORTANT]
> ポリシーは、ユーザー、グループ、またはドメインにスコープを設定できます。 3 つのポリシーすべてに一致するユーザーのみがポリシーのスコープ内に入りますので、1 つのポリシーに 3 つすべてを組み合わせることをお勧めしません。 パイロット ポリシーの場合は、グループまたはユーザーを使用することをお勧めします。 運用ポリシーの場合は、ドメインを使用することをお勧めします。 ユーザーがポリシーのスコープ内にあるかどうかを決定するのは、ユーザーのプライマリ電子メール ドメイン **のみ** であることを理解しておくことが非常に重要です。 そのため、ユーザーのセカンダリ ドメインの MX レコードを切り替える場合は、プライマリ ドメインもポリシーでカバーされていることを確認します。

### <a name="create-pilot-safe-attachments-policies"></a>パイロットの安全な添付ファイル ポリシーを作成する

[安全な添付ファイル](safe-attachments.md)は、MX レコードを切り替える前に有効にしてテストする最も簡単なDefender for Office 365機能です。 安全な添付ファイルには、次の利点があります。

- 最小限の構成。
- 誤検知の可能性が非常に低い。
- マルウェア対策保護と同様の動作。これは常にオンであり、SCL=-1 メール フロー ルールの影響を受けません。

パイロット ユーザーの安全な添付ファイル ポリシーを作成します。

推奨される設定については、「 [推奨される安全な添付ファイルのポリシー設定](recommended-settings-for-eop-and-office365.md#safe-attachments-policy-settings)」を参照してください。 Standard と Strict の推奨事項は同じであることに注意してください。 ポリシーを作成するには、「 [安全な添付ファイル ポリシーを設定する](set-up-safe-attachments-policies.md)」を参照してください。 ポリシーの条件として **グループ MDOPilot\_SafeAttachments** を使用してください (ポリシーが適用されるユーザー)。

> [!NOTE]
> **組み込みの保護** プリセット セキュリティ ポリシーは、安全な添付ファイル ポリシーで定義されていないすべての受信者に安全な添付ファイル保護を提供します。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

### <a name="create-pilot-safe-links-policies"></a>パイロット セーフ リンク ポリシーを作成する

> [!NOTE]
> 既にラップされているリンクや書き換えられたリンクの折り返しや書き換えはサポートされていません。 現在の保護サービスが既にメール メッセージ内のリンクをラップまたは書き換える場合は、パイロット ユーザーに対してこの機能を無効にする必要があります。 これが発生しないようにする 1 つの方法は、セーフ リンク ポリシーで他のサービスの URL ドメインを除外することです。

パイロット ユーザーの安全なリンク ポリシーを作成します。 セーフ リンクの誤検知の可能性も非常に低いですが、安全な添付ファイルよりも少数のパイロット ユーザーで機能をテストすることを検討する必要があります。 この機能はユーザー エクスペリエンスに影響するため、ユーザーを教育する計画を検討する必要があります。

推奨される設定については、「 [推奨されるセーフ リンク ポリシー設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)」を参照してください。 Standard と Strict の推奨事項は同じであることに注意してください。 ポリシーを作成するには、「 [安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」を参照してください。 ポリシーの条件としてグループ **MDOPilot\_SafeLinks** を使用してください (ポリシーが適用されるユーザー)。

> [!NOTE]
> **組み込みの保護** プリセット セキュリティ ポリシーは、セーフ リンク ポリシーで定義されていないすべての受信者に安全なリンク保護を提供します。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

### <a name="create-pilot-anti-spam-policies"></a>パイロットスパム対策ポリシーを作成する

パイロット ユーザー用に 2 つのスパム対策ポリシーを作成します。

- Standard 設定を使用するポリシー。 ポリシーの条件として **グループ MDOPilot\_SpamPhish\_Standard** を使用します (ポリシーが適用されるユーザー)。
- Strict 設定を使用するポリシー。 ポリシーの条件として **グループ MDOPilot\_SpamPhish\_Strict** を使用します (ポリシーが適用されるユーザー)。 このポリシーの優先度は、Standard 設定のポリシーよりも高い (数値が低い) 必要があります。

推奨される Standard と Strict の設定については、「 [推奨されるスパム対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」を参照してください。 ポリシーを作成するには、「 [スパム対策ポリシーを構成する」を](configure-your-spam-filter-policies.md)参照してください。

### <a name="create-pilot-anti-phishing-policies"></a>パイロットフィッシング対策ポリシーを作成する

パイロット ユーザー用にフィッシング対策ポリシーを 2 つ作成します。

- 次に示すように、偽装検出アクションを除き、Standard 設定を使用するポリシー。 ポリシーの条件として **グループ MDOPilot\_SpamPhish\_Standard** を使用します (ポリシーが適用されるユーザー)。
- 次に示すように、偽装検出アクションを除き、Strict 設定を使用するポリシー。 ポリシーの条件として **グループ MDOPilot\_SpamPhish\_Strict** を使用します (ポリシーが適用されるユーザー)。 このポリシーの優先度は、Standard 設定のポリシーよりも高い (数値が低い) 必要があります。

スプーフィング検出の場合、推奨される標準アクションは **、受信者の迷惑メール Email フォルダーにメッセージを移動** することです。推奨される Strict アクションは **メッセージを検疫することです**。 スプーフィング インテリジェンス分析情報を使用して結果を観察します。 オーバーライドについては、次のセクションで説明します。 詳細については、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。

偽装検出の場合は、パイロット ポリシーに推奨される Standard アクションと Strict アクションを無視します。 代わりに、次の設定に **アクションを適用しない** という値を使用します。

- **偽装されたユーザーとしてメッセージが検出された場合**
- **メッセージが偽装ドメインとして検出された場合**
- **メールボックス インテリジェンスで偽装されたユーザーが検出された場合**

偽装分析情報を使用して結果を観察します。 詳細については、「[Defender for Office 365の偽装分析情報](impersonation-insight.md)」を参照してください。

スプーフィング保護 (許可とブロックの調整) を調整し、各偽装保護アクションをオンにして、メッセージを検疫または迷惑Email フォルダーに移動します (Standard または Strict の推奨事項に基づく)。 結果を確認し、必要に応じて設定を調整できます。

詳細については、次のトピックをご覧ください。

- [スプーフィング対策保護](anti-spoofing-protection.md)
- [フィッシング対策ポリシーの偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Defender for Office 365でフィッシング対策ポリシーを構成](configure-mdo-anti-phishing-policies.md)します。

## <a name="next-step"></a>次の手順

**おめでとうございます**。 [Microsoft Defender for Office 365への移行](migrate-to-defender-for-office-365.md#the-migration-process)の **セットアップ** フェーズが完了しました。

- [フェーズ 3: オンボード](migrate-to-defender-for-office-365-onboard.md)に進みます。
