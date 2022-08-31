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
description: 管理者は、展開に関する考慮事項と、Microsoft 365 E5またはMicrosoft Defender for Office 365計画 2 組織での攻撃のシミュレーションとトレーニングに関してよく寄せられる質問について学習できます。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f0a4bf3f408b48a4feb48ae4fad39cfe1e11420d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480605"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>攻撃シミュレーション トレーニングの展開に関する考慮事項と FAQ

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)

攻撃シミュレーション トレーニングにより、Microsoft 365 E5またはMicrosoft Defender for Office 365計画 2 組織は、現実世界の非武器化されたフィッシング ペイロードを利用したフィッシング シミュレーションの作成と管理を可能にすることで、ソーシャル エンジニアリング リスクを測定および管理できます。 Terranova セキュリティと連携して提供されるハイパーターゲット トレーニングは、知識を向上させ、従業員の行動を変えるのに役立ちます。

攻撃シミュレーション トレーニングの使用の詳細については、「攻撃シミュレーション トレーニング[の使用を開始](attack-simulation-training-get-started.md)する」を参照してください。

シミュレーションの作成とスケジューリングのエクスペリエンス全体が自由に流れ、摩擦を生み出さない設計になっていますが、企業規模でシミュレーションを実行するには、多くの場合、計画が必要です。 この記事は、お客様が独自の環境でシミュレーションを実行する場合に発生する特定の課題に対処するのに役立ちます。

## <a name="issues-with-end-user-experiences"></a>エンド ユーザー エクスペリエンスに関する問題

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Google Safe Browsing によってブロックされたフィッシング シミュレーション URL

URL 評価サービスでは、攻撃シミュレーション トレーニングによって安全でないものとして使用される 1 つ以上の URL が識別される場合があります。 Google Chrome の Google Safe Browsing では、シミュレートされたフィッシング URL の一部がブロックされ、偽装 **サイトが事前** に表示されます。 多くの URL 評価ベンダーと連携して、シミュレーション URL を常に許可していますが、完全なカバレッジがあるとは限りません。

:::image type="content" source="../../media/attack-sim-training-faq-chrome-deceptive-site-message.png" alt-text="Google Chrome の偽サイト先行警告" lightbox="../../media/attack-sim-training-faq-chrome-deceptive-site-message.png":::

この問題は Microsoft Edge には影響しません。

計画フェーズの一環として、フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーで URL の可用性を確認してください。 Url が Google セーフ ブラウズによってブロックされている場合は、Google の [このガイダンスに従って](https://support.google.com/chrome/a/answer/7532419) URL へのアクセスを許可します。

[攻撃シミュレーション トレーニングで現在使用](attack-simulation-training-get-started.md)されている URL の一覧については、「攻撃シミュレーション トレーニングの使用を開始する」を参照してください。

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>ネットワーク プロキシ ソリューションとフィルター ドライバーによってブロックされたフィッシング シミュレーションと管理者の URL

フィッシング シミュレーション URL と管理者 URL の両方が、中間のセキュリティ デバイスまたはフィルターによってブロックまたは削除される可能性があります。 以下に例を示します。

- ファイアウォール
- Web Application Firewall (WAF) ソリューション
- サード パーティ製フィルター ドライバー (カーネル モード フィルターなど)

このレイヤーでブロックされているお客様はほとんどいませんが、発生します。 問題が発生した場合は、必要に応じてセキュリティ デバイスまたはフィルターによるスキャンをバイパスするように次の URL を構成することを検討してください。

- 「攻撃シミュレーション トレーニングの使用を開始する」の説明[に従ってシミュレートされた](attack-simulation-training-get-started.md)フィッシング URL。
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>ターゲットユーザー全員に配信されないシミュレーション メッセージ

シミュレーション電子メール メッセージを実際に受信するユーザーの数が、シミュレーションの対象となったユーザーの数より少ない可能性があります。 ターゲット検証の一環として、次の種類のユーザーが除外されます。

- 受信者の電子メール アドレスが無効です。
- ゲスト ユーザー。
- Azure Active Directory (Azure AD) でアクティブでなくなったユーザー。

有効なメールボックスを持つ非ゲスト ユーザーのみがシミュレーションに含まれます。 配布グループまたはメールが有効なセキュリティ グループを使用してユーザーをターゲットにする場合は、[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) の [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) コマンドレットを使用して、配布グループ のメンバーを表示および検証できます。

## <a name="issues-with-attack-simulation-training-reporting"></a>攻撃シミュレーション トレーニングレポートに関する問題

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>攻撃シミュレーション トレーニング レポートにアクティビティの詳細が含まれていない

攻撃シミュレーション トレーニングには、従業員の脅威の準備状況の進行状況を常に把握できる、実用的で豊富な分析情報が付属しています。 攻撃シミュレーション トレーニングレポートにデータが設定されていない場合は、組織で監査ログ検索が有効になっていることを確認します (既定ではオンになっています)。

イベントをキャプチャ、記録、および読み戻すことができるように、監査ログ検索は攻撃シミュレーション トレーニングで必要です。 監査ログ検索を無効にすると、攻撃シミュレーション トレーニングに対して次の結果が生まれます。

- レポート データは、すべてのレポートで使用できるわけではありません。 レポートは空で表示されます。
- データを使用できないため、トレーニングの割り当てはブロックされます。

監査ログ検索を有効にするには、「 [監査ログ検索をオンまたはオフにする」](../../compliance/turn-audit-log-search-on-or-off.md)を参照してください。

> [!NOTE]
> 空のアクティビティの詳細は、E5 ライセンスがユーザーに割り当てられていないことが原因で発生する可能性もあります。 少なくとも 1 つの E5 ライセンスがアクティブなユーザーに割り当てられていることを確認して、レポート イベントがキャプチャおよび記録されていることを確認します。

### <a name="simulation-reports-are-not-updated-immediately"></a>シミュレーション レポートは直ちに更新されない

詳細なシミュレーション レポートは、キャンペーンを開始した直後には更新されません。 心配しないでください。この動作が必要です。

すべてのシミュレーション キャンペーンにはライフサイクルがあります。 最初に作成すると、シミュレーションは **スケジュールされた** 状態になります。 シミュレーションが開始されると、 **進行中の状態** に遷移します。 完了すると、シミュレーションは **完了** 状態に遷移します。

シミュレーションが **スケジュールされた** 状態になっている間、シミュレーション レポートはほとんど空になります。 この段階では、シミュレーション エンジンによってターゲット ユーザーの電子メール アドレスの解決、配布グループの展開、ゲスト ユーザーのリストからの削除などが行われます。

:::image type="content" source="../../media/attack-sim-training-faq-scheduled-state.png" alt-text="スケジュールされた状態のシミュレーションを示すシミュレーションの詳細" lightbox="../../media/attack-sim-training-faq-scheduled-state.png":::

シミュレーションが **進行中** のステージに入ると、レポートの情報がトリクルされ始めていることがわかります。

:::image type="content" source="../../media/attack-sim-training-faq-in-progress-state.png" alt-text="進行中の状態のシミュレーションを示すシミュレーションの詳細" lightbox="../../media/attack-sim-training-faq-in-progress-state.png":::

個々のシミュレーション レポートが進行中の状態に移行した後に更新されるまでには、最大 **で** 30 分かかる場合があります。 シミュレーションが完了状態に達するまで、レポート データは引き続きビルド **されます** 。 レポートの更新は、次の間隔で行われます。

- 最初の 60 分間は 10 分おき。
- 60 分後から 2 日間 15 分ごとに行います。
- 2 日後から 7 日間まで 30 分ごとに行います。
- 7 日後に 60 分ごと。

**[概要**] ページのウィジェットには、組織のシミュレーションベースのセキュリティ体制の時間の経過に伴う簡単なスナップショットが表示されます。 これらのウィジェットは、時間の経過と共に全体的なセキュリティ体制と体験を反映するため、各シミュレーション キャンペーンが完了すると更新されます。

> [!NOTE]
> さまざまなレポート ページで **[エクスポート]** オプションを使用して、データを抽出できます。

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>ユーザーによってフィッシングとして報告されたメッセージがシミュレーション レポートに表示されない

攻撃シミュレーター トレーニングのシミュレーション レポートでは、ユーザー アクティビティの詳細が提供されます。 以下に例を示します。

- メッセージ内のリンクをクリックしたユーザー。
- 資格情報を断ち切ったユーザー。
- メッセージをフィッシングとして報告したユーザー。

ユーザーがフィッシングとして報告したメッセージが攻撃シミュレーション トレーニングシミュレーション レポートにキャプチャされない場合は、報告されたメッセージの Microsoft への配信を妨げている Exchange メール フロー ルール (トランスポート ルールとも呼ばれます) が存在する可能性があります。 メール フロー ルールによって、次のメール アドレスへの配信がブロックされていないことを確認します。

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- junk@office365.microsoft.com しない\_

### <a name="users-are-assigned-training-after-they-report-a-simulated-message"></a>シミュレートされたメッセージを報告すると、ユーザーにトレーニングが割り当てられます

ユーザーがフィッシング シミュレーション メッセージを報告した後にトレーニングが割り当てられている場合は、組織で **ユーザー送信ポリシー** で **カスタム メールボックス** が構成されているかどうかを確認します。 カスタム メールボックスを構成する場合、 **カスタム メールボックス** の前提条件に従って、このメールボックスを安全なリンクと安全な添付ファイルポリシーから除外 [する必要があります](user-submission.md)。

組織に **カスタム メールボックス** が構成されていて、必要な除外を設定していない場合、これらのメッセージが爆発し、トレーニングの割り当てが発生する可能性があります。

## <a name="other-frequently-asked-questions"></a>その他のよく寄せられる質問

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>Q: シミュレーション キャンペーンでユーザーをターゲットにする方法として推奨される方法は何ですか?

A: ターゲット ユーザーには、次のいくつかのオプションを使用できます。

- すべてのユーザーを含めます (現在、ユーザーが 40,000 人未満の組織で使用できます)。
- 特定のユーザーを選択します。
- CSV ファイルからユーザーを選択します (1 行に 1 つのメール アドレス)。
- Azure AD グループベースのターゲット設定。

ターゲットユーザーが Azure AD グループによって識別されるキャンペーンは、一般に管理が容易であることがわかりました。

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>Q: CSV からインポートしたり、ユーザーを追加したりするときに、ユーザーのターゲット設定に制限はありますか?

A: CSV ファイルから受信者をインポートするか、個々の受信者をシミュレーションに追加する場合の制限は 40,000 です。

受信者には、個々のユーザーまたはグループを指定できます。 グループには数百または数千の受信者が含まれている可能性があるため、実際の制限は個々のユーザーの数に設定されません。

大きな CSV ファイルを管理したり、多くの個々の受信者を追加したりするのは面倒な場合があります。 Azure AD グループを使用すると、シミュレーションの全体的な管理が簡略化されます。

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>Q: Microsoft は他の言語でペイロードを提供していますか?

A: 現在、ローカライズされたペイロードは、中国語 (簡体字)、中国語 (繁体字)、英語、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語、ロシア語、スペイン語、オランダ語の 40 以上の言語で使用できます。 既存のペイロードを他の言語に直接翻訳または機械翻訳すると、不正確さが生じ、関連性が低下することがわかります。

つまり、カスタム ペイロード作成エクスペリエンスを使用して、任意の言語で独自のペイロードを作成できます。 また、特定の地域のユーザーをターゲットにするために使用された既存のペイロードを収集することを強くお勧めします。 つまり、攻撃者がコンテンツをローカライズできるようにします。

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>Q: 管理者ポータルとトレーニング エクスペリエンスの他の言語に切り替えるにはどうすればよいですか。

A: Microsoft 365 またはOffice 365では、言語構成はユーザー アカウントごとに固有で一元化されています。 言語設定を変更する方法については、「 [Microsoft 365 for Business で表示言語とタイム ゾーンを変更](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)する」を参照してください。

すべてのサービス間で同期するには、構成の変更に最大 30 分かかる場合があることに注意してください。

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>Q: 本格的なキャンペーンを開始する前に、テスト シミュレーションをトリガーして、その外観を理解することはできますか?

A: はい、 新しいシミュレーションを作成するためのウィザードの最後の [シミュレーションの **確認** ] ページには、 **テストを送信** するオプションがあります。 このオプションは、現在ログインしているユーザーにサンプルフィッシング シミュレーション メッセージを送信します。 受信トレイでフィッシング メッセージを検証したら、シミュレーションを送信できます。

:::image type="content" source="../../media/attack-sim-training-simulations-review-simulation.png" alt-text="[シミュレーションの確認] ページの [テストの送信] ボタン" lightbox="../../media/attack-sim-training-simulations-review-simulation.png":::

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>Q: 同じシミュレーション キャンペーンの一環として、別のテナントに属するユーザーをターゲットにできますか?

回答: いいえ。 現在、テナント間シミュレーションはサポートされていません。 対象となるすべてのユーザーが同じテナント内にあることを確認します。 クロステナント ユーザーまたはゲスト ユーザーは、シミュレーション キャンペーンから除外されます。

### <a name="q-how-does-region-aware-delivery-work"></a>Q: リージョン対応の配信のしくみ

A: リージョン対応の配信では、ターゲット ユーザーのメールボックスの TimeZone 属性と "not before" ロジックを使用して、メッセージを配信するタイミングを決定します。 たとえば、次のシナリオを考えてみましょう。

- 太平洋タイム ゾーン (UTC-8) の午前 7 時 00 分に、管理者はキャンペーンを作成し、同じ日の午前 9 時に開始するようにスケジュールを設定します。
- UserA は東部タイム ゾーン (UTC-5) にあります。
- UserB は太平洋タイム ゾーンにも含まれます。

同じ日の午前 9 時に、シミュレーション メッセージが UserB に送信されます。 リージョン対応の配信では、メッセージは同じ日に UserA に送信されません。太平洋時間の午前 9:00 は東部時間の午後 12:00 であるためです。 代わりに、メッセージは、次の日の東部時間の午前 9 時に UserA に送信されます。

そのため、リージョン対応配信が有効になっているキャンペーンの初回実行時に、シミュレーション メッセージが特定のタイム ゾーンのユーザーにのみ送信されたように見える場合があります。 ただし、時間が経過し、スコープに入るユーザーが増えるにつれて、対象ユーザーは増加します。


### <a name="q-does-microsoft-collect-or-store-any-information-that-users-enter-at-the-credential-harvest-sign-in-page-used-in-the-credential-harvest-simulation-technique"></a>Q: Microsoft では、資格情報の収集シミュレーション手法で使用される資格情報の収集サインイン ページでユーザーが入力した情報を収集または保存しますか?

回答: いいえ。 資格情報の収集ログイン ページに入力されたすべての情報は、サイレント モードで破棄されます。 侵害イベントをキャプチャするために記録されるのは、"クリック" のみです。 Microsoft は、この手順でユーザーが入力した詳細を収集、記録、または保存しません。
