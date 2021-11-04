---
title: 'Microsoft Defender に移行して、Office 365フェーズ 3: オンボード'
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
description: サード パーティ製の保護サービスまたはデバイスから Microsoft Defender に移行する手順を実行して、Office 365します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a218aa1e86bd696079bb2c77b630bcf870bc0c25
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60779190"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-3-onboard"></a>Microsoft Defender に移行して、Office 365 - フェーズ 3: オンボード

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

<br>

|[![フェーズ 1: 準備します。](../../media/phase-diagrams/prepare.png)](migrate-to-defender-for-office-365-prepare.md) <br> [フェーズ 1: 準備](migrate-to-defender-for-office-365-prepare.md)|[![フェーズ 2: セットアップ。](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [フェーズ 2: 設定](migrate-to-defender-for-office-365-setup.md)|![フェーズ 3: オンボード。](../../media/phase-diagrams/onboard.png) <br> フェーズ 3: オンボード|
|---|---|---|
|||*お前はここにいる!*|

フェーズ **3 へようこそ: Microsoft** **[Defender](migrate-to-defender-for-office-365.md#the-migration-process)** への移行にOffice 365! この移行フェーズには、次の手順が含まれます。

1. [セキュリティ ポリシーのオンボーディングをTeams](#step-1-begin-onboarding-security-teams)
2. [(省略可能)パイロット ユーザーが既存の保護サービスによるフィルター処理を除外する](#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)
3. [スプーフィング インテリジェンスの調整](#step-3-tune-spoof-intelligence)
4. [偽装保護とメールボックス インテリジェンスの調整](#step-4-tune-impersonation-protection-and-mailbox-intelligence)
5. [ユーザー申請のデータを使用して測定と調整を行う](#step-5-use-data-from-user-submissions-to-measure-and-adjust)
6. [(省略可能)パイロットにユーザーを追加して反復処理する](#step-6-optional-add-more-users-to-your-pilot-and-iterate)
7. [すべてのMicrosoft 365保護を拡張し、SCL=-1 メール フロー ルールをオフにする](#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)
8. [MX レコードを切り替える](#step-8-switch-your-mx-records)

## <a name="step-1-begin-onboarding-security-teams"></a>手順 1: セキュリティ ポリシーのオンボーディングを開始Teams

組織にセキュリティ対応チームがある場合は、チケットシステムを含む、Office 365の Microsoft Defender の統合を開始します。 これは、それ自体に関するトピック全体ですが、見落とされがちです。 セキュリティ対応チームを早期に参加することで、MX レコードを切り替える際に組織が脅威に対処する準備ができていることを確認できます。 インシデント対応は、次のタスクを処理するために十分な設備が必要です。

- 新しいツールを学習し、既存のフローに統合します。 例:
  - 検疫済みメッセージの管理は重要です。 手順については、「検疫済み [メッセージとファイルを管理者として管理する」を参照してください](manage-quarantined-messages-and-files.md)。
  - メッセージ トレースを使用すると、メッセージの入力時または退出時にメッセージに何が起こったMicrosoft 365。 詳細については、「Exchange 管理センターのメッセージ トレース」[を参照Exchange Online。](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
- 組織に入れ込む可能性のあるリスクを特定します。
- 組織プロセスの [アラートを調整](../../compliance/alert-policies.md) およびカスタマイズします。
- インシデント キューを管理し、潜在的なリスクを修復します。

組織が microsoft Defender for Office 365 Plan 2 を購入している場合は、脅威エクスプローラー、高度な狩猟、インシデントなどの機能について理解し、使用する必要があります。 関連するトレーニングについては、を参照してください <https://aka.ms/mdoninja> 。

セキュリティ応答チームがフィルター処理されていないメッセージを収集して分析する場合は、これらのフィルター処理されていないメッセージを受信する SecOps メールボックスを構成できます。 手順については、「高度な配信 [ポリシーで SecOps メールボックスを構成する」を参照してください](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)。

### <a name="siemsoar"></a>SIEM/SOAR

SIEM/SOAR との統合の詳細については、次の記事を参照してください。

- [Microsoft 365 Defender API の概要](/microsoft-365/security/defender/api-overview)
- [ストリーミング API](/microsoft-365/security/defender/streaming-api)
- [高度な追求 API](/microsoft-365/security/defender/api-advanced-hunting)
- [インシデント API](/microsoft-365/security/defender/api-incident)

組織にセキュリティ対応チームや既存のプロセス フローが存在しない場合は、この時間を使用して、Defender for Office 365 の基本的なハンティングおよび応答機能について理解することができます。 詳細については、「脅威の調査 [と対応」を参照してください](office-365-ti.md)。

### <a name="rbac-roles"></a>RBAC ロール

Defender for Office 365のアクセス許可は、役割ベースのアクセス制御 (RBAC) に基づいており、このポータルの [アクセス許可][でMicrosoft 365 Defenderされています](permissions-microsoft-365-security-center.md)。 以下に注意する重要な点を示します。

- Azure ADロールは、すべてのワークロードにアクセス許可を付与Microsoft 365。 たとえば、Azure portal のセキュリティ管理者にユーザーを追加すると、すべての場所にセキュリティ管理者のアクセス許可が付与されます。
- & ポータルMicrosoft 365 Defenderの共同作業ロールにメールを送信すると、Microsoft 365 Defender ポータル、Microsoft 365 コンプライアンス センター、および以前のセキュリティ & コンプライアンス センターにアクセス許可が付与されます。 たとえば、Microsoft 365 Defender ポータルでセキュリティ管理者にユーザーを追加すると、Microsoft 365 Defender ポータル、Microsoft 365 コンプライアンス センター、セキュリティ &コンプライアンス センターでのみセキュリティ管理者アクセス権が与わります。
- Microsoft 365 Defender ポータルの多くの機能は Exchange Online PowerShell コマンドレットに基づくため、Exchange Online の対応する役割 (技術的には役割グループ) の役割グループ メンバーシップが必要です (特に、対応するサーバーへのアクセスExchange OnlinePowerShell コマンドレット)。
- Microsoft 365 Defender ポータルには、Azure AD ロールと同等の役割を持たない電子メール & コラボレーション ロールが含まれます。セキュリティ操作 (プレビュー ロールや検索と削除の役割など) では重要です。

通常、セキュリティ担当者のサブセットのみが、ユーザー メールボックスから直接メッセージをダウンロードする追加の権限を必要とします。 これには、セキュリティ リーダーに既定で付与されていない追加のアクセス許可が必要です。

## <a name="step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service"></a>手順 2: (オプション) パイロット ユーザーが既存の保護サービスによるフィルター処理を除外する

この手順は必須ではありませんが、既存の保護サービスによるフィルター処理をバイパスするパイロット ユーザーの構成を検討する必要があります。 このアクションにより、Defender for Office 365パイロット ユーザー **のすべてのフィルター処理** と保護の義務を処理できます。 パイロット ユーザーを既存の保護サービスから除外しない場合、Defender for Office 365 は他のサービスからのミス (既にフィルター処理されたメッセージのフィルター処理) でのみ効果的に動作します。

> [!NOTE]
> 現在の保護サービスでリンクの折り返しを提供しているが、リンク機能を試用する場合は、この手順セーフ必要です。 リンクの二重折り返しはサポートされていません。

## <a name="step-3-tune-spoof-intelligence"></a>手順 3: スプーフィング インテリジェンスを調整する

スプー [フィング インテリジェンス](learn-about-spoof-intelligence.md) の分析情報を確認して、スプーフィングとして許可またはブロックされている情報を確認し、スプーフィングのシステムの評決を上書きする必要があるかどうかを判断します。 ビジネスクリティカルな電子メールの一部のソースでは、DNS (SPF、DKIM、DMARC) で電子メール認証レコードが正しく構成されていない可能性があります。また、既存の保護サービスで上書きを使用してドメインの問題をマスクしている可能性があります。

スプーフィング インテリジェンスは、DNS の適切な電子メール認証レコードなしでドメインから電子メールを救出できますが、この機能では、適切なスプーフィングと悪いスプーフィングを区別するための支援が必要な場合があります。 次の種類のメッセージ ソースに注目します。

- [コネクタの拡張フィルター] で定義されている IP アドレス範囲 [の外部にある](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)メッセージ ソース。
- メッセージの数が最も多いメッセージ ソース。
- 組織に最も大きな影響を与えるメッセージ ソース。

スプーフィング インテリジェンスは、ユーザーの申請を構成した後に最終的に調整されます。そのため、完璧な機能を必要としません。

## <a name="step-4-tune-impersonation-protection-and-mailbox-intelligence"></a>手順 4: 偽装保護とメールボックス インテリジェンスを調整する

[アクション モードを適用しない] で偽装保護の結果を確認するのに十分な時間が取られたら、フィッシング対策ポリシーで偽装保護アクションを個別に有効にできます。

- ユーザー偽装保護: Standard **と** Strict の両方のメッセージを検疫します。
- ドメイン偽装保護: Standard **と** Strict の両方のメッセージを検疫します。
- メールボックス インテリジェンス保護: **メッセージを受信者の** 標準の迷惑メール フォルダーに移動します。 **[厳密] のメッセージを** 検疫します。

偽装保護の結果をメッセージに対して処理せずに監視する時間が長くなると、必要になる可能性のある許可またはブロックを特定する必要があるデータが多くなります。 観察と調整を可能にするのに十分な大きな各保護をオンにする間の遅延を使用してください。

> [!NOTE]
> これらの保護の頻繁で継続的な監視と調整が重要です。 誤検知が疑われる場合は、原因を調査し、必要に応じて上書きのみを使用し、必要な検出機能のみを使用します。

### <a name="tune-mailbox-intelligence"></a>メールボックス インテリジェンスの調整

メールボックス インテリジェンスは、偽装の試行と判断されたメッセージに対[](impersonation-insight.md)して何もアクションを実行するように構成されていませんが、パイロット ユーザーの電子メールの送受信パターンをオンにし、学習しています。 外部ユーザーがパイロット ユーザーの 1 人と接触している場合、その外部ユーザーからのメッセージは、メールボックス インテリジェンスによる偽装の試みとして識別されません (したがって、誤検知が減少します)。

準備ができたら、次の手順を実行して、偽装の試行として検出されたメッセージに対してメールボックス インテリジェンスが機能します。

- 標準保護設定のフィッシング対策ポリシーで、[メールボックス インテリジェンスが偽装ユーザーを検出した場合] の値を変更して、受信者の迷惑メール フォルダーにメッセージを **移動します**。

- [厳密な保護] 設定のフィッシング対策ポリシーで、[メールボックス インテリジェンスが検出され偽装されたユーザーの場合] の値を [メッセージの検疫 **] に変更します**。

ポリシーを変更するには[、「Defender で](configure-mdo-anti-phishing-policies.md)フィッシング対策ポリシーを構成する」を参照Office 365。

結果を確認し、調整を行った後、次のセクションに進み、ユーザー偽装によって検出されたメッセージを検疫します。

### <a name="tune-user-impersonation-protection"></a>ユーザー偽装保護の調整

Standard と Strict の設定に基づくフィッシング対策ポリシーの両方で、[メッセージが偽装されたユーザーとして検出された場合] の値を [メッセージの検疫]**に変更します**。

偽装の [分析情報を](impersonation-insight.md) 確認して、ユーザー偽装の試みとしてブロックされている情報を確認します。

ポリシーを変更するには[、「Defender で](configure-mdo-anti-phishing-policies.md)フィッシング対策ポリシーを構成する」を参照Office 365。

結果を確認し、調整を行った後、次のセクションに進み、ドメイン偽装によって検出されたメッセージを検疫します。

### <a name="tune-domain-impersonation-protection"></a>ドメイン偽装保護の調整

Standard と Strict の設定に基づくフィッシング対策ポリシーの両方で、[メッセージが偽装ドメインとして検出された場合] の値を [メッセージの検疫]**に変更します**。

偽装の [分析情報を確認](impersonation-insight.md) して、ドメイン偽装の試みとしてブロックされている情報を確認します。

ポリシーを変更するには[、「Defender で](configure-mdo-anti-phishing-policies.md)フィッシング対策ポリシーを構成する」を参照Office 365。

結果を確認し、必要に応じて調整を行います。

## <a name="step-5-use-data-from-user-submissions-to-measure-and-adjust"></a>手順 5: ユーザー申請のデータを使用して測定および調整する

パイロット ユーザーが誤検知と誤検知を報告すると、メッセージはポータルの [申請][ページにMicrosoft 365 Defenderされます](admin-submission.md)。 誤認されたメッセージを分析のために Microsoft に報告し、情報を使用してパイロット ポリシーの設定と例外を必要に応じて調整できます。

Defender の保護設定を監視および反復処理するには、次の機能を使用Office 365。

- [検疫](manage-quarantined-messages-and-files.md)
- [脅威エクスプローラー](email-security-in-microsoft-defender.md)
- [電子メール セキュリティ レポート](view-email-security-reports.md)
- [レポートのOffice 365ディフェンダー](view-reports-for-mdo.md)
- [メール フローの分析情報](/exchange/monitoring/mail-flow-insights/mail-flow-insights)
- [メール フロー レポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

組織がユーザー レポートにサードパーティ サービスを使用している場合は、そのデータをフィードバック ループに統合できます。

## <a name="step-6-optional-add-more-users-to-your-pilot-and-iterate"></a>手順 6: (オプション) パイロットにユーザーを追加して反復処理する

問題を見つけて修正すると、パイロット グループにユーザーを追加できます (それに対応して、新しいパイロット ユーザーが既存の保護サービスによるスキャンを適切に除外します)。 テストを行う度に、後で対処する必要があるユーザーの問題が少なめになります。 この "ウォーターフォール" アプローチでは、組織の大部分に対して調整を行い、セキュリティ チームが新しいツールとプロセスに合わせて調整する時間を与えます。

- Microsoft 365ポリシーによって信頼度の高いフィッシング メッセージが許可されている場合にアラートを生成します。 これらのメッセージを識別するには、次のオプションがあります。
  - 脅威保護の状態 [レポートの上書き](view-email-security-reports.md#threat-protection-status-report)。
  - 脅威エクスプローラーでフィルターを実行して、メッセージを識別します。
  - 高度な検索でフィルター処理して、メッセージを識別します。

  管理者の申請を通じて、可能な限り早期に誤検知を Microsoft に報告し、テナント許可 [/](tenant-allow-block-list.md) ブロック一覧機能を使用して、それらの誤検知に対する安全な上書きを構成します。

- また、不要な上書きを調べるのも良い考えです。 つまり、メッセージで提供されたMicrosoft 365を確認します。 Microsoft365 が正しい評決をレンダリングした場合、オーバーライドの必要性は大幅に減少または排除されます。

## <a name="step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule"></a>手順 7: すべてのMicrosoft 365保護を拡張し、SCL=-1 メール フロー ルールをオフにする

MX レコードを新しいレコードに切り替える準備ができたら、このセクションの手順を実行Microsoft 365。

1. パイロット ポリシーを組織全体に拡張します。 基本的に、これを行う方法は異なります。
   - 事前 [に設定されたセキュリティ](preset-security-policies.md) ポリシーを使用し、標準保護プロファイルと厳密な保護プロファイルの間でユーザーを分割します (すべてのユーザーが対象に設定されている必要があります)。 事前設定されたセキュリティ ポリシーは、作成したカスタム ポリシーまたは既定のポリシーの前に適用されます。 個々のパイロット ポリシーを削除せずにオフにできます。

     セキュリティ ポリシーを事前に設定する欠点は、重要な設定の多くを作成した後で変更できない点です。

   - パイロット中に作成および調整したポリシーの範囲を変更して、すべてのユーザー (すべてのドメイン内のすべての受信者など) を含める。 同じ種類の複数のポリシー (フィッシング対策ポリシーなど) が同じユーザー (個別、グループ メンバーシップ、または電子メール ドメイン) に適用される場合は、優先度が最も高いポリシーの設定 (優先度が最も低い番号) だけが適用され、その種類のポリシーの処理が停止します。

2. SCL=-1 メール フロー ルールをオフにします (削除せずにオフにできます)。

3. 以前の変更が有効にされ、すべてのユーザーに対して Defender for Office 365が正しく有効になっているか確認します。 この時点で、Office 365 用 Defender のすべての保護機能は、すべての受信者のメールに対して処理が許可されますが、そのメールは既存の保護サービスによって既にスキャンされています。

この段階で一時停止して、より大規模なデータの記録とチューニングを行います。

## <a name="step-8-switch-your-mx-records"></a>手順 8: MX レコードを切り替える

> [!NOTE]
>
> - ドメインの MX レコードを切り替える場合、変更がインターネット全体に反映されるのに最大 48 時間かかることがあります。
>
> - DNS レコードの TTL 値を下げて、応答の高速化とロールバックを可能にすることをお勧めします (必要な場合)。 切り替えが完了して検証された後は、元の TTL 値に戻す必要があります。
>
> - 使用頻度の低いドメインの変更から始める必要があります。 大きなドメインに移動する前に、一時停止して監視できます。 ただし、この場合でも、セカンダリ SMTP ドメインはポリシー アプリケーションの前にプライマリ ドメインに解決されるので、すべてのユーザーとドメインがポリシーでカバーされている必要があります。
>   
> - 1 つのドメインの複数の MX レコードが技術的に機能し、この記事のすべてのガイダンスに従っている場合は、分割ルーティングが可能です。 具体的には、「セットアップ 手順 [3: SCL=-1](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)メール フロー ルールを維持または作成する」の説明に従って、ポリシーがすべてのユーザーに適用され、SCL=-1 メール フロー ルールが既存の保護サービスを通過するメールにのみ適用される必要があります。 ただし、この構成ではトラブルシューティングが非常に困難になる動作が導入されるため、通常は、特に長時間は推奨しません。
>
> - MX レコードを切り替える前に、保護サービスから受信コネクタで次の設定が有効になっていないMicrosoft 365。 通常、コネクタには次の 1 つ以上の設定が構成されます。
>
>   - **パートナーが認証に使用** する証明書のサブジェクト名が、このドメインOffice 365一致する必要があります (*RestrictDomainsToCertificate*)
>   - **この IP アドレス範囲内から** 送信されない電子メール メッセージを拒否する (*RestrictDomainsToIPAddresses*)
>
>   コネクタの種類が **Partner** で、これらの設定のいずれかをオンにすると、MX レコードを切り替えても、ドメインへのメール配信はすべて失敗します。 続行する前に、これらの設定を無効にする必要があります。 コネクタがハイブリッドに使用されるオンプレミス コネクタの場合は、オンプレミス コネクタを変更する必要があります。 ただし、パートナー コネクタの有無を **確認** できます。
>   
> - 現在のメール ゲートウェイで受信者の検証も行っている場合は、ドメインが権限のあるドメインとして構成[](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)されていることを確認Microsoft 365。 これにより、不要なバウンス メッセージを防止できます。

準備ができたら、ドメインの MX レコードを切り替えます。 すべてのドメインを一度に移行できます。 または、使用頻度の低いドメインを最初に移行し、残りのドメインを後で移行することもできます。

いつでもここで一時停止して評価してください。 ただし、SCL=-1 メール フロー ルールをオフにした場合、ユーザーは誤検知をチェックする 2 つの異なるエクスペリエンスを持つ可能性があります。 1 つの一貫性のあるエクスペリエンスを提供できると、ユーザーとヘルプ デスク チームは、不足しているメッセージのトラブルシューティングを行う必要がある場合に、より幸せになります。

## <a name="next-steps"></a>次の手順

おめでとうございます! Microsoft Defender への移行が完了[しました。Office 365!](migrate-to-defender-for-office-365.md#the-migration-process) この移行ガイドの手順に従ったので、メールが直接メールで配信される最初の数日間は、Microsoft 365よりスムーズになる必要があります。

次に、Defender の通常の操作とメンテナンスを開始し、Office 365。 パイロットの間に経験した問題に似ているが、より大規模な問題を監視し、監視します。 ス [プーフィング インテリジェンスの分析](learn-about-spoof-intelligence.md) 情報と [偽装の分析情報](impersonation-insight.md) が最も役立ちますが、次のアクティビティを定期的に実行する方法を検討してください。

- ユーザーの申請、特にユーザーが報告 [したフィッシング メッセージを確認します](/microsoft-365/security/office-365-security/automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)。
- 脅威保護の状態レポート [で上書きを確認します](view-email-security-reports.md#threat-protection-status-report)。
- 高度 [なハンティング クエリ](/microsoft-365/security/defender/advanced-hunting-example.md) を使用して、調整の機会と危険なメッセージを探します。
