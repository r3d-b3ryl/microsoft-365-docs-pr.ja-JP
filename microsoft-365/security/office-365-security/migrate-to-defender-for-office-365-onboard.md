---
title: 'Microsoft Defender for Office 365 フェーズ 3: オンボードに移行する'
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
description: サード パーティの保護サービスまたはデバイスからMicrosoft Defender for Office 365保護に移行する手順を完了します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d30f13e77f0b7da864d266ddb2607afe7de1d451
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388089"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-3-onboard"></a>Microsoft Defender for Office 365に移行する - フェーズ 3: オンボード

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

<br>

|[![フェーズ 1: 準備します。](../../media/phase-diagrams/prepare.png#lightbox)](migrate-to-defender-for-office-365-prepare.md) <br> [フェーズ 1: 準備](migrate-to-defender-for-office-365-prepare.md)|[![フェーズ 2: セットアップします。](../../media/phase-diagrams/setup.png#lightbox)](migrate-to-defender-for-office-365-setup.md) <br> [フェーズ 2: 設定](migrate-to-defender-for-office-365-setup.md)|![フェーズ 3: オンボード。](../../media/phase-diagrams/onboard.png) <br> フェーズ 3: オンボード|
|---|---|---|
|||*お客様はここにいます。*|

**フェーズ 3 へようこそ:****[Microsoft Defender for Office 365への移行](migrate-to-defender-for-office-365.md#the-migration-process)** をオンボードします。 この移行フェーズには、次の手順が含まれます。

1. [Security Teams のオンボードを開始する](#step-1-begin-onboarding-security-teams)
2. [(省略可能)既存の保護サービスによるフィルター処理からパイロット ユーザーを除外する](#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)
3. [スプーフィング インテリジェンスを調整する](#step-3-tune-spoof-intelligence)
4. [偽装保護とメールボックス インテリジェンスを調整する](#step-4-tune-impersonation-protection-and-mailbox-intelligence)
5. [ユーザー提出のデータを使用して測定と調整を行う](#step-5-use-data-from-user-submissions-to-measure-and-adjust)
6. [(省略可能)パイロットにユーザーを追加して反復処理する](#step-6-optional-add-more-users-to-your-pilot-and-iterate)
7. [Microsoft 365 の保護をすべてのユーザーに拡張し、SCL=-1 メール フロールールを無効にする](#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)
8. [MX レコードを切り替える](#step-8-switch-your-mx-records)

## <a name="step-1-begin-onboarding-security-teams"></a>手順 1: Security Teams のオンボードを開始する

組織にセキュリティ対応チームがある場合は、チケット発行システムを含む応答プロセスへのMicrosoft Defender for Office 365の統合を開始します。 これはトピック全体ですが、見落とされることがあります。 セキュリティ対応チームを早期に取得することで、MX レコードを切り替える際に組織が脅威に対処する準備が整います。 次のタスクを処理するには、インシデント対応を十分に備える必要があります。

- 新しいツールを学習し、それらを既存のフローに統合します。 例:
  - 検疫されたメッセージの管理管理重要です。 手順については、「 [管理者として検疫されたメッセージとファイルを管理する」を参照してください](manage-quarantined-messages-and-files.md)。
  - メッセージ トレースを使用すると、メッセージが Microsoft 365 に出入りするときに何が起こったかを確認できます。 詳細については、[Exchange Onlineの最新の Exchange 管理センターのメッセージ トレースに関する説明を](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)参照してください。
- 組織に任せられている可能性のあるリスクを特定します。
- 組織のプロセスの [アラート](../../compliance/alert-policies.md) を調整してカスタマイズします。
- インシデント キューを管理し、潜在的なリスクを修復します。

組織がプラン 2 Microsoft Defender for Office 365購入した場合は、Threat Explorer、Advanced Hunting、Incidents などの機能について理解し、使用し始める必要があります。 関連するトレーニングについては、以下を参照してください <https://aka.ms/mdoninja>。

セキュリティ応答チームがフィルター処理されていないメッセージを収集して分析する場合は、これらのフィルター処理されていないメッセージを受信するように SecOps メールボックスを構成できます。 手順については、「 [高度な配信ポリシーで SecOps メールボックスを構成する](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)」を参照してください。

### <a name="siemsoar"></a>SIEM/SOAR

SIEM/SOAR との統合の詳細については、次の記事を参照してください。

- [Microsoft 365 Defender API の概要](/microsoft-365/security/defender/api-overview)
- [ストリーミング API](/microsoft-365/security/defender/streaming-api)
- [高度な追求 API](/microsoft-365/security/defender/api-advanced-hunting)
- [インシデント API](/microsoft-365/security/defender/api-incident)

組織にセキュリティ対応チームまたは既存のプロセス フローがない場合は、この時間を使用して、Defender for Office 365の基本的なハンティング機能と応答機能について理解することができます。 詳細については、「 [脅威の調査と対応](office-365-ti.md)」を参照してください。

### <a name="rbac-roles"></a>RBAC ロール

Defender for Office 365のアクセス許可はロールベースのアクセス制御 (RBAC) に基づいており、[Microsoft 365 Defender ポータル](permissions-microsoft-365-security-center.md)のアクセス許可で説明されています。 次の点に留意する必要があります。

- Azure AD ロールは、Microsoft 365 **のすべての** ワークロードにアクセス許可を付与します。 たとえば、Azure portalのセキュリティ管理者にユーザーを追加すると、すべての場所でセキュリティ管理者のアクセス許可が付与されます。
- Microsoft 365 Defender ポータルのコラボレーション ロールEmail &、Microsoft 365 Defender ポータル、Microsoft Purview コンプライアンス ポータル、および以前のセキュリティ & コンプライアンス センターにアクセス許可を付与します。 たとえば、Microsoft 365 Defender ポータルでセキュリティ管理者にユーザーを追加すると、Microsoft 365 Defender ポータル、Microsoft Purview コンプライアンス ポータル、セキュリティ & コンプライアンス センター **でのみ** セキュリティ管理者にアクセスできます。
- Microsoft 365 Defender ポータルの多くの機能は、Exchange Online PowerShell コマンドレットに基づいているため、Exchange Onlineの対応するロール (技術的には、役割グループ) のロール グループ メンバーシップが必要です (特に、対応するExchange Online PowerShell コマンドレット)。
- Microsoft 365 Defender ポータルには、Azure AD ロールに相当しないEmail &コラボレーション ロールがあり、セキュリティ操作 (プレビュー ロールや検索ロールや消去ロールなど) に重要です。

通常、セキュリティ担当者のサブセットのみが、ユーザー メールボックスから直接メッセージをダウンロードするための追加の権限を必要とします。 これには、Security Reader に既定で付与されていない追加のアクセス許可が必要です。

## <a name="step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service"></a>手順 2: (省略可能) パイロット ユーザーが既存の保護サービスによるフィルター処理を除外する

この手順は必要ありませんが、既存の保護サービスによるフィルター処理をバイパスするようにパイロット ユーザーを構成することを検討する必要があります。 このアクションにより、Defender for Office 365はパイロット ユーザー **のすべての** フィルター処理と保護の職務を処理できます。 パイロット ユーザーを既存の保護サービスから除外しない場合、Defender for Office 365他のサービスからのミス (既にフィルター処理されているメッセージのフィルター処理) でのみ効果的に動作します。

> [!NOTE]
> 現在の保護サービスがリンク ラッピングを提供しているが、安全なリンク機能をパイロットする場合は、この手順が明示的に必要です。 リンクの二重折り返しはサポートされていません。

## <a name="step-3-tune-spoof-intelligence"></a>手順 3: スプーフィング インテリジェンスを調整する

[スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)を確認して、スプーフィングとして許可またはブロックされているものを確認し、スプーフィングのシステム判定をオーバーライドする必要があるかどうかを判断します。 ビジネスクリティカルな電子メールの一部のソースで、DNS (SPF、DKIM、DMARC) で電子メール認証レコードが正しく構成されておらず、既存の保護サービスでオーバーライドを使用してドメインの問題をマスクしている可能性があります。

スプーフィング インテリジェンスは、DNS で適切な電子メール認証レコードを使用せずにドメインから電子メールを救済できますが、この機能では、スプーフィングと不適切なスプーフィングを区別するための支援が必要な場合があります。 次の種類のメッセージ ソースに焦点を当てます。

- [コネクタの拡張フィルター処理](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)で定義されている IP アドレス範囲外のメッセージ ソース。
- メッセージの数が最も多いメッセージ ソース。
- 組織に最も大きな影響を与えるメッセージ ソース。

スプーフィング インテリジェンスは、最終的にユーザーの送信を構成した後に自身を調整するため、完璧な操作を行う必要はありません。

## <a name="step-4-tune-impersonation-protection-and-mailbox-intelligence"></a>手順 4: 偽装保護とメールボックス インテリジェンスを調整する

アクション モードを **適用しない** で偽装保護の結果を確認するのに十分な時間が経過したら、フィッシング対策ポリシーで各偽装保護アクションを個別に有効にすることができます。

- ユーザー権限借用保護: Standard と Strict **の両方のメッセージを検疫** します。
- ドメイン偽装保護: Standard と Strict **の両方のメッセージを検疫** します。
- メールボックス インテリジェンス保護: **受信者の迷惑メール Email フォルダーにメッセージを移動** します。**Strict のメッセージを検疫** します。

メッセージに作用せずに偽装保護の結果を監視する時間が長いほど、必要な可能性がある許可またはブロックを特定する必要があるデータが増えます。 観察と調整を可能にするために十分に重要な各保護をオンにするまでの遅延を使用することを検討してください。

> [!NOTE]
> これらの保護の頻繁かつ継続的な監視とチューニングが重要です。 誤検知が疑われる場合は、原因を調査し、必要な場合にのみオーバーライドを使用し、それを必要とする検出機能に対してのみ使用します。

### <a name="tune-mailbox-intelligence"></a>メールボックス インテリジェンスを調整する

メールボックス インテリジェンスは [、偽装試行と判断](impersonation-insight.md)されたメッセージに対してアクションを実行するように構成されていますが、パイロット ユーザーの電子メール送受信パターンがオンになっていると学習されています。 外部ユーザーがパイロット ユーザーと連絡を取っている場合、その外部ユーザーからのメッセージは、メールボックス インテリジェンスによる偽装の試行として識別されません (したがって、誤検知が減ります)。

準備ができたら、次の手順を実行して、偽装試行として検出されたメッセージに対してメールボックス インテリジェンスが動作できるようにします。

- Standard Protection 設定のフィッシング対策ポリシーで、[**メールボックス インテリジェンスが偽装されたユーザーを検出した場合**] の値を変更して、**メッセージを受信者の迷惑Email フォルダーに移動します**。

- Strict Protection 設定のフィッシング対策ポリシーで、[ **メールボックス インテリジェンスが検出して偽装されたユーザーの場合** ] の値を **[メッセージの検疫]** に変更します。

ポリシーを変更するには、「[Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

結果を観察して調整を行った後は、次のセクションに進み、ユーザーの偽装によって検出されたメッセージを検疫します。

### <a name="tune-user-impersonation-protection"></a>ユーザー権限借用保護を調整する

Standard と Strict の設定に基づくフィッシング対策ポリシーの両方で、 **偽装されたユーザーとしてメッセージが検出された場合** の値を [ **メッセージを検疫する]** に変更します。

[偽装の分析情報](impersonation-insight.md)を確認して、ユーザー偽装の試行時にブロックされている内容を確認します。

ポリシーを変更するには、「[Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

結果を観察して調整を行った後は、次のセクションに進み、ドメイン偽装によって検出されたメッセージを検疫します。

### <a name="tune-domain-impersonation-protection"></a>ドメイン偽装保護を調整する

Standard と Strict の設定に基づくフィッシング対策ポリシーの両方で、 **偽装されたドメインとしてメッセージが検出された場合** の値を [ **メッセージの検疫]** に変更します。

[偽装の分析情報](impersonation-insight.md)を確認して、ドメイン偽装の試行としてブロックされている内容を確認します。

ポリシーを変更するには、「[Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

結果を確認し、必要に応じて調整を行います。

## <a name="step-5-use-data-from-user-submissions-to-measure-and-adjust"></a>手順 5: ユーザー提出のデータを使用して測定および調整する

パイロット ユーザーが誤検知と偽陰性を報告すると、Microsoft 365 Defender [ポータルの [提出] ページにメッセージが](admin-submission.md)表示されます。 誤認されたメッセージを分析のために Microsoft に報告し、必要に応じてパイロット ポリシーの設定と例外を調整する情報を使用できます。

Defender for Office 365の保護設定を監視および反復処理するには、次の機能を使用します。

- [検疫](manage-quarantined-messages-and-files.md)
- [脅威エクスプローラー](email-security-in-microsoft-defender.md)
- [Email セキュリティ レポート](view-email-security-reports.md)
- [Defender for Office 365 レポート](view-reports-for-mdo.md)
- [メール フローの分析情報](/exchange/monitoring/mail-flow-insights/mail-flow-insights)
- [メール フロー レポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

組織がユーザー レポートにサード パーティのサービスを使用している場合は、そのデータをフィードバック ループに統合できます。

## <a name="step-6-optional-add-more-users-to-your-pilot-and-iterate"></a>手順 6: (省略可能) パイロットにユーザーを追加し、反復処理する

問題を見つけて修正すると、パイロット グループにユーザーを追加できます (また、新しいパイロット ユーザーが既存の保護サービスによるスキャンを適宜除外することもできます)。 テストを行うほど、後で対処する必要があるユーザーの問題は少なくなります。 この "ウォーターフォール" アプローチにより、組織の大部分に対するチューニングが可能になり、セキュリティ チームは新しいツールやプロセスに調整する時間を与えます。

- Microsoft 365 では、組織のポリシーで信頼度の高いフィッシング メッセージが許可されている場合にアラートが生成されます。 これらのメッセージを識別するには、次のオプションがあります。
  - [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)のオーバーライド。
  - 脅威エクスプローラーでフィルター処理してメッセージを識別します。
  - Advanced Hunting でフィルター処理してメッセージを識別します。

  管理者の提出を通じてできるだけ早く Microsoft に誤検知を報告し、 [テナント許可/ブロック リスト](manage-tenant-allow-block-list.md) 機能を使用して、これらの誤検知の安全な上書きを構成します。

- また、不要なオーバーライドを調べることもお勧めします。 言い換えると、Microsoft 365 がメッセージに対して提供した評決を確認します。 Microsoft365 が正しい判定を下した場合、オーバーライドの必要性は大幅に減少または排除されます。

## <a name="step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule"></a>手順 7: Microsoft 365 の保護をすべてのユーザーに拡張し、SCL=-1 メール フロー ルールを無効にする

MICROSOFT 365 を指すように MX レコードを切り替える準備ができたら、このセクションの手順を実行します。

1. パイロット ポリシーを組織全体に拡張します。 基本的に、これを行うにはさまざまな方法があります。
   - [事前設定されたセキュリティ](preset-security-policies.md) ポリシーを使用し、Standard 保護プロファイルと Strict 保護プロファイルの間でユーザーを分割します (全員が対象になっていることを確認してください)。 事前設定されたセキュリティ ポリシーは、作成したカスタム ポリシーまたは既定のポリシーの前に適用されます。 個々のパイロット ポリシーを削除せずに無効にすることができます。

     事前設定されたセキュリティ ポリシーの欠点は、重要な設定の多くを作成した後で変更できないことです。

   - パイロット中に作成および調整したポリシーのスコープを、すべてのユーザー (すべてのドメイン内のすべての受信者など) を含めるために変更します。 同じ種類の複数のポリシー (フィッシング対策ポリシーなど) が同じユーザー (グループ メンバーシップ、または電子メール ドメインによって個別に) に適用される場合は、優先度が最も高いポリシーの設定 (優先度が最も低い番号) のみが適用され、その種類のポリシーの処理が停止します。

2. SCL=-1 メール フロー ルールをオフにします (削除せずに無効にすることができます)。

3. 前の変更が有効になっており、Defender for Office 365がすべてのユーザーに対して適切に有効になっていることを確認します。 この時点で、Defender for Office 365のすべての保護機能は、すべての受信者のメールに対して動作できるようになりましたが、そのメールは既存の保護サービスによって既にスキャンされています。

この段階で一時停止すると、より大規模なデータの記録とチューニングを行うことができます。

## <a name="step-8-switch-your-mx-records"></a>手順 8: MX レコードを切り替える

> [!NOTE]
>
> - ドメインの MX レコードを切り替えると、変更がインターネット全体に反映されるまでに最大で 48 時間かかる場合があります。
> - 応答の高速化とロールバック (必要な場合) を有効にするために、DNS レコードの TTL 値を下げることをお勧めします。 切り替えが完了して検証された後、元の TTL 値に戻すことができます。
> - 使用頻度の低いドメインの変更から始めることをお勧めします。 大規模なドメインに移行する前に、一時停止と監視を行うことができます。 ただし、これを行う場合でも、セカンダリ SMTP ドメインはポリシー アプリケーションの前にプライマリ ドメインに解決されるため、すべてのユーザーとドメインがポリシーでカバーされていることを確認する必要があります。
> - 1 つのドメインに対して複数の MX レコードが技術的に機能するため、この記事のすべてのガイダンスに従っている場合は、分割ルーティングを行うことができます。 具体的には、「セットアップ 手順 3: SCL=-1 メール フロー ルールを維持または作成する」の説明に従って、既存の保護サービスを通過するメールにのみ [SCL=-1 メール フロー ルール](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)が適用されるように、すべてのユーザーにポリシーが適用されていることを確認する必要があります。 ただし、この構成ではトラブルシューティングをはるかに困難にする動作が導入されるため、通常は推奨されません。特に長時間の場合は推奨されません。
> - MX レコードを切り替える前に、保護サービスから Microsoft 365 への受信コネクタで次の設定が有効になっていないことを確認します。 通常、コネクタには次の 1 つ以上の設定が構成されます。
>   - **パートナーがOffice 365で認証するために使用する証明書のサブジェクト名がこのドメイン名と一致することを要求** します (*RestrictDomainsToCertificate*)
>   - この IP アドレス範囲 (*RestrictDomainsToIPAddresses*) **内から送信されない場合は、電子メール メッセージを拒否** します。コネクタの種類が **パートナー** であり、これらの設定のいずれかが有効になっている場合、MX レコードを切り替えた後、ドメインへのすべてのメール配信が失敗します。 続行する前に、これらの設定を無効にする必要があります。 コネクタがハイブリッドに使用されるオンプレミス コネクタの場合は、オンプレミス コネクタを変更する必要はありません。 ただし、 **パートナー** コネクタの存在を確認することはできます。
> - 現在のメール ゲートウェイで受信者の検証も提供されている場合は、ドメインが Microsoft 365 で [[権限あり]](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) として構成されていることを確認することをお勧めします。 これにより、不要なバウンス メッセージを防ぐことができます。

準備ができたら、ドメインの MX レコードを切り替えます。 すべてのドメインを一度に移行できます。 または、使用頻度の低いドメインを最初に移行してから、後で残りのドメインを移行することもできます。

任意の時点で、ここで自由に一時停止して評価してください。 ただし、SCL=-1 メール フロー ルールをオフにすると、ユーザーは誤検知をチェックするための 2 つの異なるエクスペリエンスを持つ可能性があることに注意してください。 1 つの一貫性のあるエクスペリエンスをすぐに提供できる限り、ユーザーとヘルプ デスク チームは、不足しているメッセージのトラブルシューティングを行う必要があるとき、より幸せになります。

## <a name="next-steps"></a>次の手順

おめでとうございます。 [Microsoft Defender for Office 365への移行](migrate-to-defender-for-office-365.md#the-migration-process)が完了しました。 この移行ガイドの手順に従ったので、メールが Microsoft 365 に直接配信される最初の数日間は、はるかにスムーズである必要があります。

次に、Defender for Office 365の通常の操作とメンテナンスを開始します。 パイロットの間に発生した問題と似ていますが、大規模な問題を監視して監視します。 [スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)と[偽装分析情報](impersonation-insight.md)が最も役立ちますが、次のアクティビティを定期的に発生することを検討してください。

- ユーザーの提出、特に [ユーザーから報告されたフィッシング メッセージを確認する](automated-investigation-response-office.md)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)で上書きを確認します。
- [高度なハンティング](/microsoft-365/security/defender/advanced-hunting-example) クエリを使用して、チューニングの機会と危険なメッセージを探します。
