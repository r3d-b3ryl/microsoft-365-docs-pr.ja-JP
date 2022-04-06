---
title: 攻撃シミュレーション トレーニングの展開に関する考慮事項と FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection: m365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft 365 E5 または Microsoft Defender for Office 365 プラン 2 組織の攻撃シミュレーションとトレーニングに関する展開に関する考慮事項とよく寄せられる質問について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 57b4d684e52fd51a2ece279cc7322389a953a17c
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467799"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>攻撃シミュレーション トレーニングの展開に関する考慮事項と FAQ

Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 組織は、実際の武器化されたフィッシング ペイロードを利用したフィッシング シミュレーションの作成と管理を可能にすることで、ソーシャル エンジニアリング リスクを測定および管理できます。 テラノバ のセキュリティと提携して提供されるハイパーターゲットトレーニングは、知識の向上と従業員の行動の変更に役立ちます。

攻撃シミュレーション トレーニングの概要については、「攻撃シミュレーション トレーニングの使用を開始 [する」を参照してください](attack-simulation-training-get-started.md)。

シミュレーションの作成とスケジューリングの全体のエクスペリエンスは、自由に流れ、摩擦のない状態で設計されているが、企業規模でシミュレーションを実行するには計画が必要な場合が多い。 この記事は、お客様が独自の環境でシミュレーションを実行する場合に見る特定の課題に対処するのに役立ちます。

## <a name="issues-with-end-user-experiences"></a>エンド ユーザー エクスペリエンスに関する問題

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Google セーフ ブラウズによってブロックされるフィッシング シミュレーション URL

URL レピュテーション サービスは、攻撃シミュレーション トレーニングで使用される 1 つ以上の URL を安全でないと識別する場合があります。 Google セーフ Chrome での閲覧は、詐欺サイトの先行メッセージを使用して、シミュレートされたフィッシング URL の一部 **をブロック** します。 多くの URL レピュテーション ベンダーと一緒にシミュレーション URL を常に許可しますが、必ずしも完全にカバーできるとは限らない。

:::image type="content" source="../../media/attack-sim-training-faq-chrome-deceptive-site-message.png" alt-text="Google Chrome の Deceptive サイト先行警告" lightbox="../../media/attack-sim-training-faq-chrome-deceptive-site-message.png":::

この問題は、この問題に影響Microsoft Edge。

計画フェーズの一環として、フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーの URL の可用性を確認してください。 Google セーフブラウズによって URL がブロックされている場合は、Google からこのガイダンス[](https://support.google.com/chrome/a/answer/7532419)に従って URL へのアクセスを許可します。

現在攻撃 [シミュレーション トレーニングで](attack-simulation-training-get-started.md) 使用されている URL の一覧については、「攻撃シミュレーション トレーニングの使用を開始する」を参照してください。

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>ネットワーク プロキシ ソリューションとフィルター ドライバーによってブロックされるフィッシング シミュレーションと管理 URL

フィッシング シミュレーション URL と管理 URL の両方が、中間セキュリティ デバイスまたはフィルターによってブロックまたは削除される可能性があります。 次に例を示します。

- ファイアウォール
- Web アプリケーション ファイアウォール (WAF) ソリューション
- サード パーティ製フィルター ドライバー (カーネル モード フィルターなど)

このレイヤーでブロックされているお客様は少ない一方で、発生します。 問題が発生した場合は、必要に応じて、セキュリティ デバイスまたはフィルターによるスキャンをバイパスする次の URL を構成してください。

- 「攻撃シミュレーショントレーニングの使用を開始する」の説明に従って、シミュレート [されたフィッシング URL](attack-simulation-training-get-started.md)。
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>すべての対象ユーザーに配信されないシミュレーション メッセージ

シミュレーション電子メール メッセージを実際に受信するユーザーの数が、シミュレーションの対象となったユーザーの数よりも少ない可能性があります。 次の種類のユーザーは、ターゲットの検証の一部として除外されます。

- 受信者の電子メール アドレスが無効です。
- ゲスト ユーザー。
- 現在アクティブでなくなったユーザー (Azure Active Directory) Azure AD。

有効なメールボックスを持つゲスト以外のユーザーだけがシミュレーションに含まれます。 配布グループまたはメールが有効なセキュリティ グループを使用してユーザーを対象とする場合は、[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) の [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) コマンドレットを使用して配布グループメンバーを表示および検証できます。

## <a name="issues-with-attack-simulation-training-reporting"></a>攻撃シミュレーショントレーニングレポートの問題

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>攻撃シミュレーションのトレーニング レポートにアクティビティの詳細が含まれている

攻撃シミュレーションのトレーニングには、豊富でアクション可能な分析情報が付属し、従業員の脅威の準備状況の進捗状況を知らせ続ける必要があります。 攻撃シミュレーション トレーニング レポートにデータが入力されていない場合は、組織内で監査ログ検索が有効になっていることを確認します (既定ではオンになっています)。

監査ログの検索は、イベントをキャプチャ、記録、および読み取り戻しできるよう、攻撃シミュレーション トレーニングで必要です。 監査ログ検索をオフにした場合、攻撃シミュレーション トレーニングでは次の結果が発生します。

- レポート データは、すべてのレポートで使用できるとは言えな。 レポートは空に表示されます。
- データを使用できないので、トレーニングの割り当てがブロックされます。

監査ログ検索を有効にする方法については、「 [監査ログ検索を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

> [!NOTE]
> 空のアクティビティの詳細は、E5 ライセンスがユーザーに割り当てられていない場合にも発生します。 少なくとも 1 つの E5 ライセンスがアクティブ ユーザーに割り当てられているのを確認して、レポート イベントがキャプチャおよび記録されます。

### <a name="simulation-reports-are-not-updated-immediately"></a>シミュレーション レポートが直ちに更新されない

詳細なシミュレーション レポートは、キャンペーンを開始した直後には更新されません。 心配しないでください。この動作が予期されます。

すべてのシミュレーション キャンペーンにはライフサイクルがあります。 最初に作成すると、シミュレーションはスケジュールされた **状態** になります。 シミュレーションが開始されると、進行中の状態 **に移行** します。 完了すると、シミュレーションは完了状態 **に移行** します。

シミュレーションがスケジュールされた状態 **の間** 、シミュレーション レポートはほとんどの場合空になります。 この段階では、シミュレーション エンジンはターゲット ユーザーの電子メール アドレスを解決し、配布グループを展開し、リストからゲスト ユーザーを削除します。

:::image type="content" source="../../media/attack-sim-training-faq-scheduled-state.png" alt-text="スケジュールされた状態のシミュレーションを示すシミュレーションの詳細" lightbox="../../media/attack-sim-training-faq-scheduled-state.png":::

シミュレーションが進行中のステージ **に入** った後、レポートにトリクルを開始する情報が表示されます。

:::image type="content" source="../../media/attack-sim-training-faq-in-progress-state.png" alt-text="進行中の状態のシミュレーションを示すシミュレーションの詳細" lightbox="../../media/attack-sim-training-faq-in-progress-state.png":::

個々のシミュレーション レポートが進行中の状態に移行した後に更新するには、最大 30 分 **かかる場合** があります。 シミュレーションが完了状態に達するまで、レポート データは引き続 **き作成** されます。 レポートの更新は、次の間隔で行われます。

- 最初の 60 分間は 10 分ごとに。
- 60 分後から 2 日まで 15 分ごとに。
- 2 日後から 7 日まで 30 分ごとに。
- 7 日後に 60 分ごとに。

[概要] **ページのウィジェット** は、組織のシミュレーション ベースのセキュリティ体制の概要を時間の間に提供します。 これらのウィジェットは、全体的なセキュリティの姿勢と時間の長い旅を反映しますので、各シミュレーション キャンペーンの完了後に更新されます。

> [!NOTE]
> さまざまなレポート ページの **[エクスポート]** オプションを使用して、データを抽出できます。

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>ユーザーがフィッシングとして報告したメッセージがシミュレーション レポートに表示されない

攻撃シミュレーター トレーニングのシミュレーション レポートでは、ユーザーのアクティビティに関する詳細を提供します。 次に例を示します。

- メッセージ内のリンクをクリックしたユーザー。
- 資格情報を渡したユーザー。
- メッセージをフィッシングとして報告したユーザー。

ユーザーがフィッシングとして報告したメッセージが攻撃シミュレーション シミュレーション レポートでキャプチャされない場合、報告されたメッセージの Microsoft への配信をブロックしている Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) がある可能性があります。 メール フロー ルールが次のメール アドレスへの配信をブロックしていないか確認します。

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- not\_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>その他のよく寄せられる質問

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>Q: シミュレーション キャンペーンでユーザーをターゲットに設定する推奨方法は何ですか?

A: ターゲット ユーザーに使用できるオプションは複数あります。

- すべてのユーザーを含める (現在、40,000 人未満のユーザーを持つ組織で利用可能)。
- 特定のユーザーを選択します。
- CSV ファイル (1 行に 1 つのメール アドレス) からユーザーを選択します。
- Azure ADベースのターゲット設定。

対象となるユーザーがグループによって識別されるキャンペーンは、通常、Azure AD簡単に管理できると分かっています。

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>Q: CSV からインポートする場合やユーザーを追加する場合、ユーザーのターゲット設定に制限はありますか?

A: CSV ファイルから受信者をインポートするか、個々の受信者をシミュレーションに追加する制限は 40,000 です。

受信者には、個々のユーザーまたはグループを指定できます。 グループには数百人または数千人の受信者が含まれている可能性があります。したがって、実際の制限は個々のユーザーの数に設定されません。

大きな CSV ファイルを管理したり、多数の個々の受信者を追加したりすると、面倒な場合があります。 グループAzure AD使用すると、シミュレーションの全体的な管理が簡略化されます。

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>Q: Microsoft は他の言語でペイロードを提供していますか?

A: 現在、40 以上のローカライズされたペイロードは、中国語 (簡体字)、中国語 (繁体字)、英語、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語、ロシア語、スペイン語、オランダ語の 10 以上の言語で利用できます。 既存のペイロードを他の言語に直接翻訳または機械翻訳すると、不正確で関連性が低下する可能性があります。

つまり、カスタム ペイロードの作成エクスペリエンスを使用して、選択した言語で独自のペイロードを作成できます。 また、特定の地域のユーザーをターゲットにするために使用された既存のペイロードを収集することを強く推奨します。 つまり、攻撃者がコンテンツをローカライズします。

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>Q: 管理ポータルとトレーニング エクスペリエンスのために他の言語に切り替える方法を教えてください。

A: ユーザー Microsoft 365またはOffice 365、言語の構成はユーザー アカウントごとに固有で集中管理されています。 言語設定を変更する方法については、「ビジネス向けページで表示言語とタイム ゾーンを変更する[Microsoft 365参照してください](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)。

すべてのサービス間で同期するには、構成の変更に最大で 30 分かかる場合があります。

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>Q: 本格的なキャンペーンを開始する前に、テスト シミュレーションをトリガーして、その外観を把握できますか?

A: はい、可能です。 ウィザードの最後 **の [シミュレーションの** 確認] ページで、新しいシミュレーションを作成するには、テストを送信 **するオプションがあります**。 このオプションは、現在ログインしているユーザーにフィッシング シミュレーション メッセージのサンプルを送信します。 受信トレイでフィッシング メッセージを検証した後、シミュレーションを送信できます。

:::image type="content" source="../../media/attack-sim-training-simulations-review-simulation.png" alt-text="[シミュレーションの確認] ページの [テストの送信] ボタン" lightbox="../../media/attack-sim-training-simulations-review-simulation.png":::

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>Q: 同じシミュレーション キャンペーンの一環として、別のテナントに属するユーザーをターゲットにできますか?

A: いいえ。 現在、テナント間シミュレーションはサポートされていません。 すべての対象ユーザーが同じテナントに入っていることを確認します。 テナント間のユーザーまたはゲスト ユーザーは、シミュレーション キャンペーンから除外されます。

### <a name="q-how-does-region-aware-delivery-work"></a>Q: 地域対応配信の動作について

A: 地域対応配信では、対象ユーザーのメールボックスの TimeZone 属性を使用し、メッセージを配信する時期を決定するために "前に" ロジックを使用します。 たとえば、次のシナリオを考えます。

- 太平洋タイム ゾーン (UTC-8) の午前 7 時に、管理者はキャンペーンを作成し、同じ日の午前 9 時に開始するスケジュールを設定します。
- UserA は東部タイム ゾーン (UTC-5) にあります。
- UserB は太平洋のタイム ゾーンにもいます。

同じ日の午前 9 時に、シミュレーション メッセージが UserB に送信されます。 地域対応の配信では、太平洋時間午前 9:00 は東部時間の午後 12:00 なので、メッセージは同じ日に UserA に送信されません。 代わりに、メッセージは、次の日の東部時間の午前 9:00 に UserA に送信されます。

そのため、地域に対応した配信が有効になっているキャンペーンの最初の実行では、シミュレーション メッセージが特定のタイム ゾーンのユーザーにのみ送信された可能性があります。 ただし、時間が経過し、スコープに入るユーザーが増えるほど、対象となるユーザーは増加します。
