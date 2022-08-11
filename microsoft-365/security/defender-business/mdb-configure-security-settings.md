---
title: Microsoft Defender for Businessでセキュリティ設定を表示および編集する
description: Defender for Business でセキュリティ ポリシーと設定を表示および編集する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: f7530cd06f2d41ed4ef3fcc12daa5f89e2903c94
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300435"
---
# <a name="view-and-edit-security-policies-and-settings-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでセキュリティ ポリシーと設定を表示および編集する

会社のデバイスを Defender for Business にオンボードしたら、次の手順ではセキュリティ ポリシーを確認します。 

> [!TIP]
> Defender for Business には、推奨される設定を含む事前構成済みのセキュリティ ポリシーが含まれています。 これらの設定は、ビジネス ニーズに合わせて編集できます。

確認および構成するセキュリティ ポリシーは次のとおりです。

- 会社のデバイスのウイルス対策とマルウェア対策の保護を決定する **[次世代保護ポリシー](#view-or-edit-your-next-generation-protection-policies)**
- **[ファイアウォールの保護とルール](#view-or-edit-your-firewall-policies-and-custom-rules)**。会社のデバイスとの間で送受信できるネットワーク トラフィックを決定します。
- **[成人コンテンツ](#set-up-web-content-filtering)** や法的責任などのカテゴリに基づいて特定の Web サイト (URL) にアクセスできないようにする Web コンテンツ フィルター
- ブロック モードでの自動調査と応答、エンドポイントの検出と応答 (EDR) などの **[高度な機能](#review-settings-for-advanced-features)**

Defender for Business では、デバイス [グループ](mdb-create-edit-device-groups.md#what-is-a-device-group)を介してデバイスにセキュリティ ポリシーが適用されます。 

セキュリティ ポリシーに加えて、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で使用するタイム ゾーンや、プレビュー機能が使用可能になった時点で受信するかどうかなどの[設定を表示および編集](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)できます。

この記事は、セキュリティ ポリシーと設定を管理するためのガイドとして使用します。

## <a name="what-to-do"></a>操作

1. [セキュリティ ポリシーとデバイスを管理する場所の選択](#choose-where-to-manage-security-policies-and-devices)。
2. [次世代の保護ポリシーを確認します](#view-or-edit-your-next-generation-protection-policies)。
3. [ファイアウォール ポリシーとカスタムルールを確認します](#view-or-edit-your-firewall-policies-and-custom-rules)。
4. [Web コンテンツ フィルターを設定する](#set-up-web-content-filtering)。
5. [高度な機能の設定の確認](#review-settings-for-advanced-features)。
6. [Microsoft 365 Defender ポータルで他の設定を表示します](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)。 
7. [次の手順に進みます](#next-steps)。


## <a name="choose-where-to-manage-security-policies-and-devices"></a>セキュリティ ポリシーとデバイスを管理する場所を選択する

Defender for Business は、セットアップと構成プロセスを効率化するのに役立つ [簡略化された](mdb-simplified-configuration.md) 構成プロセスを備えています。 簡略化された構成プロセスを選択した場合は、Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) でセキュリティ ポリシーを表示および管理できます。 ただし、このオプションに限定されるわけではありません。 Microsoft Intuneを使用している場合は、Microsoft エンドポイント マネージャー管理センターを引き続き使用できます。

次の表は、セキュリティ ポリシーとデバイスを管理する場所を選択するのに役立ちます。

| オプション | 説明 |
|:---|:---|
| **Microsoft 365 Defender ポータルを使用する**  | Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) は、会社のデバイス、セキュリティ ポリシー、およびセキュリティ設定を管理するためのワンストップ ショップです。 セキュリティ ポリシーと設定にアクセスし、 [脅威&脆弱性管理ダッシュボード](mdb-view-tvm-dashboard.md)を使用し、インシデントをすべて 1 か所で [表示および管理](mdb-view-manage-incidents.md) できます。 <br/><br/>Intuneを使用している場合は、Defender for Business にオンボードしたデバイスとセキュリティ ポリシーがエンドポイント マネージャー管理センターに表示されます。 詳細については、次の記事を参照してください。<ul><li>[Defender for Business の既定の設定とMicrosoft Intune](mdb-next-gen-configuration-settings.md#defender-for-business-default-settings-and-microsoft-intune)</li><li>[Defender for Business のファイアウォール](mdb-firewall.md)</li></ul>   |
| **Microsoft エンドポイント マネージャー管理センターを使用する** | 会社で既にIntuneを使用してセキュリティ ポリシーを管理している場合は、エンドポイント マネージャー管理センターを引き続き使用して、デバイスとセキュリティ ポリシーを管理できます。 詳細については、「Microsoft Intuneの[エンドポイント セキュリティ ポリシーを使用したデバイス セキュリティの管理](/mem/intune/protect/endpoint-security-policy)」を参照してください。 <br/><br/>[Defender for Business で簡略化された構成プロセス](mdb-simplified-configuration.md)に切り替える場合は、後でポリシーの[競合](mdb-troubleshooting.yml)を回避するために、Intune内の既存のセキュリティ ポリシーをすべて削除するように求められます。 |

> [!IMPORTANT]
> Microsoft 365 Defender ポータルでセキュリティ ポリシーを管理している場合は、エンドポイント マネージャー管理センター () でこれらのポリシーを *表示* できます。[https://endpoint.microsoft.com](https://endpoint.microsoft.com)このポリシーは **ウイルス対策** ポリシーまたは **ファイアウォール** ポリシーとして一覧表示されます。 管理センターでファイアウォール ポリシーを表示すると、ファイアウォール保護用のポリシーとカスタム ルール用のポリシーの 2 つのポリシーが一覧表示されます。

## <a name="view-or-edit-your-next-generation-protection-policies"></a>次世代の保護ポリシーを表示または編集する

Microsoft 365 Defender ポータルを使用しているか、Microsoft エンドポイント マネージャー管理センターを使用して次世代保護ポリシーを管理しているかに応じて、次のいずれかの手順を使用します。

| portal | プロシージャ |
|:---|:---|
| Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) |<ol><li>Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。</li><li>ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 ポリシーは、オペレーティング システムとポリシーの種類によって編成されます。</li><li>オペレーティング システム タブ ( **Windows クライアント** など) を選択します。</li><li>**次世代保護を** 展開して、ポリシーの一覧を表示します。</li><li>ポリシーを選択して、ポリシーの詳細を表示します。</li><li>変更を加えたり、ポリシー設定の詳細を確認したりするには、次の記事を参照してください。 <ul><li>[デバイス ポリシーを表示または編集する](mdb-view-edit-policies.md)</li><li>[次世代の構成設定を理解する](mdb-next-gen-configuration-settings.md)</li></ul></li><ol>  |
| Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) |Intuneでセキュリティ設定を管理する方法については、Microsoft Intune[のエンドポイント セキュリティの管理から](/mem/intune/protect/endpoint-security)始めます。 <ol><li>[https://endpoint.microsoft.com](https://endpoint.microsoft.com) に移動し、サインインします。 これで、エンドポイント マネージャー管理センターに入るようになりました。</li><li>[ **エンドポイント セキュリティ] を選択します**。</li><li>**[ウイルス対策]** を選択して、そのカテゴリのポリシーを表示します。</li></ol>|

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>ファイアウォール ポリシーとカスタム ルールを表示または編集する

Microsoft 365 Defender ポータルを使用しているか、Microsoft エンドポイント マネージャー管理センターを使用してファイアウォール保護を管理しているかに応じて、次のいずれかの手順に従います。

| portal | プロシージャ |
|:---|:---|
| Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) |<ol><li>Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。</li><li>ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 ポリシーは、オペレーティング システムとポリシーの種類によって編成されます。</li><li>オペレーティング システム タブ ( **Windows クライアント** など) を選択します。</li><li>**ファイアウォール** を展開して、ポリシーの一覧を表示します。</li><li>詳細を表示するポリシーを選択します。 </li><li>変更を加えたり、ポリシー設定の詳細を確認したりするには、次の記事を参照してください。<ul><li>[デバイス ポリシーを表示または編集する](mdb-view-edit-policies.md)</li><li>[ファイアウォールの設定](mdb-firewall.md)</li><li>[ファイアウォール ポリシーのカスタム ルールを管理する](mdb-custom-rules-firewall.md)</li><ul></li><ol>  |
| Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) |Intuneでセキュリティ設定を管理する方法については、Microsoft Intune[のエンドポイント セキュリティの管理から](/mem/intune/protect/endpoint-security)始めます。 <ol><li>[https://endpoint.microsoft.com](https://endpoint.microsoft.com) に移動し、サインインします。 これで、エンドポイント マネージャー管理センターに入るようになりました。</li><li>[ **エンドポイント セキュリティ] を選択します**。</li><li>**[ファイアウォール**] を選択して、そのカテゴリのポリシーを表示します。 ファイアウォール保護用に定義されたカスタム規則は、個別のポリシーとして一覧表示されます。</li></ol>|

## <a name="set-up-web-content-filtering"></a>Web コンテンツ フィルターを設定する

Web コンテンツ フィルターを使用すると、セキュリティ チームは、次のようなコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。

- **成人向けコンテンツ**: カルト、賭け行為、ヌード、ポルノ、性的に明示的な資料、または暴力に関連するサイト
- **高帯域幅**: サイト、イメージ共有サイト、またはピアツーピア ホストをダウンロードする
- **法的責任**: 児童の不正使用画像を含むサイト、違法な行為の促進、盗用または学校の不正行為を促進するサイト、または有害な活動を促進するサイト
- **娯楽**: Web ベースのチャット ルーム、オンライン ゲーム、Web ベースの電子メール、ソーシャル ネットワークを提供するサイト
- **分類されていない**: コンテンツがないサイト、または新しく登録されたサイト

これらのカテゴリのすべての Web サイトが悪意のあるとは限りませんが、コンプライアンス規制、帯域幅の使用、またはその他の懸念があるため、会社にとって問題になる可能性があります。 監査専用ポリシーを作成して、セキュリティ チームが Web サイトカテゴリをブロックする必要があるかどうかをよりよく理解することができます。

Web コンテンツ のフィルター処理は、主要な Web ブラウザーで利用できます。このブロックは、Windows Defender SmartScreen (Microsoft Edge) と Network Protection (Chrome、Firefox、Brave、Opera) によって実行されます。 詳細については、「 [Web コンテンツ フィルターの前提条件」](../defender-endpoint/web-content-filtering.md#prerequisites)を参照してください。

### <a name="to-set-up-web-content-filtering"></a>Web コンテンツ フィルターを設定するには

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、[**設定****Web コンテンツ フィルター+ ポリシーの** > **追加]** >  を選択します。

2. ポリシーの名前と説明を指定します。

3. ブロックするカテゴリを選択します。 展開アイコンを使用して各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。 Web サイトをブロックしない監査専用ポリシーを設定するには、カテゴリを選択しないでください。 **[Uncategorized]** を選択しないでください。

4. ポリシーを適用するデバイス グループを選択して、ポリシー スコープを指定します。 選択したデバイス グループ内のデバイスのみが、選択したカテゴリの Web サイトにアクセスできなくなります。

5. 概要を確認し、ポリシーを保存します。 ポリシーの更新は、選択したデバイスに適用されるまでに最大 2 時間かかる場合があります。

> [!TIP]
> Web コンテンツ のフィルター処理の詳細については、「 [Web コンテンツ のフィルター処理](../defender-endpoint/web-content-filtering.md)」を参照してください。

## <a name="review-settings-for-advanced-features"></a>高度な機能の設定を確認する

Defender for Business には、次世代の保護、ファイアウォール、Web コンテンツ フィルタリング ポリシーに加えて、高度なセキュリティ機能が含まれています。 これらの機能は、推奨される設定に事前構成されています。 これらの設定を確認し、ビジネス ニーズに合わせて編集することができます。

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で高度な機能の設定にアクセスするには **、Settings** > **Endpoints** > **の一般的** > **な高度な機能** にアクセスします。

次の表では、高度な機能設定について説明します。

| Setting | 説明 |
|:---|:---|
| **自動調査** <br/>(既定でオンになっています) | アラートが生成されると、自動調査が発生する可能性があります。 各自動調査では、検出された脅威にアクションが必要かどうかを判断し、ファイルの検疫への送信、プロセスの停止、デバイスの分離、URL のブロックなどの修復アクションを実行または推奨します。 調査の実行中に関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。 影響を受けるエンティティが他の場所で見られる場合、自動調査はそのエンティティを含むようにその範囲を拡大し、調査プロセスが繰り返されます。<br/><br/>[ **インシデント]** ページで調査を表示できます。 インシデントを選択し、[調査] タブ **を** 選択します。<br/><br/>既定では、自動調査機能と応答機能がテナント全体で有効になっています。 **自動調査を有効にしておくことをお勧めします**。 オフにすると、Microsoft Defender ウイルス対策のリアルタイム保護が影響を受け、全体的な保護レベルが低下します。 <br/><br/>[自動調査の詳細については、こちらを参照してください](../defender-endpoint/automated-investigations.md)。   |
| **ライブ応答**  | Defender for Business には、次の種類の手動応答アクションが含まれています。 <ul><li>ウイルス対策スキャンの実行</li><li>デバイスの分離</li><li>ファイルを停止して検疫する</li><li>ファイルをブロックまたは許可するインジケーターを追加する</li></ul> <br/><br/>[応答アクションの詳細については、こちらを参照してください](../defender-endpoint/respond-machine-alerts.md)。 |
| **サーバーのライブ応答** | (この設定は、現在 Defender for Business では使用できません。   |
| **Live Response unsigned スクリプトの実行** | (この設定は、現在 Defender for Business では使用できません。  | 
| **ブロック モードで EDR を有効にする**<br/>(既定でオンになっています) | Microsoft Defender ウイルス対策がプライマリウイルス対策製品ではなく、デバイスでパッシブ モードで実行されている場合に、悪意のあるアーティファクトからの保護を強化します。 ブロック モードのエンドポイント検出と応答 (EDR) は、EDR 機能によって検出された悪意のあるアーティファクトを修復するためにバックグラウンドで機能します。 このような成果物は、Microsoft 以外のプライマリウイルス対策製品によって見逃されている可能性があります。<br/><br/>[ブロック モードでの EDR の詳細については、こちらを参照してください](../defender-endpoint/edr-in-block-mode.md)。 |
| **ファイルを許可またはブロックする** <br/>(既定でオンになっています) | インジケーターを使用してファイルを許可またはブロック [できるようにします](../defender-endpoint/indicator-file.md)。 この機能では、Microsoft Defender ウイルス対策がアクティブ モードで、 [クラウド保護](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md) が有効になっている必要があります。<br/><br/>ファイルをブロックすると、組織内のデバイスで読み取り、書き込み、または実行できなくなります。 <br/><br/>[ファイルのインジケーターの詳細について説明します](../defender-endpoint/indicator-file.md)。  |
| **カスタム ネットワーク インジケーター**<br/>(既定でオンになっています) | [ネットワーク インジケーター](../defender-endpoint/indicator-ip-domain.md)を使用して、IP アドレス、URL、またはドメインを許可またはブロックできるようにします。 この機能では、Microsoft Defender ウイルス対策がアクティブ モードで、 [ネットワーク保護](../defender-endpoint/enable-network-protection.md) が有効になっている必要があります。<br/><br/>脅威インテリジェンスに基づいて、IP、URL、またはドメインを許可またはブロックできます。 リスクの高いアプリを開いた場合にユーザーにメッセージを表示することもできますが、プロンプトによってアプリの使用が停止されることはありません。<br/><br/>[ネットワーク保護の詳細については、こちらを参照してください](../defender-endpoint/network-protection.md)。 |
| **改ざん防止**<br/>(この設定をオンにすることをお勧めします) | 改ざん防止により、悪意のあるアプリが次のようなアクションを実行できなくなります。<ul><li>ウイルスと脅威の保護を無効にする</li><li>リアルタイム保護を無効にする</li><li>動作の監視を無効にする</li><li>クラウド保護を無効にする</li><li>セキュリティ インテリジェンス更新プログラムを削除する</li><li>検出された脅威に対する自動アクションを無効にする</li></ul><br/><br/>改ざん防止は、本質的に Microsoft Defender ウイルス対策をセキュリティで保護された既定値にロックし、アプリや承認されていない方法によってセキュリティ設定が変更されないようにします。 <br/><br/>[改ざん防止の詳細については、こちらを参照してください](../defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection.md)。  |
| **ユーザーの詳細を表示する**<br/>(既定でオンになっています) | 組織内のユーザーが、従業員の写真、名前、役職、部署などの詳細を表示できるようにします。 これらの詳細は、Azure Active Directory (Azure AD) に格納されます。<br/><br/>[Azure AD のユーザー プロファイルの詳細について説明します](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。  |
| **Skype for Business統合**<br/>(既定でオンになっています) | Skype for Businessは 2021 年 7 月に廃止されました。 Microsoft Teams にまだ移行していない場合は、「 [小規模ビジネスでの Microsoft Teams のセットアップ](/microsoftteams/deploy-small-business)」を参照してください。 <br/><br/>Microsoft Teams (または以前のSkype for Business) との統合により、ビジネス内のユーザー間のワンクリック通信が可能になります。   |
| **Web コンテンツ フィルタリング**<br/>(既定でオンになっています) | 不要なコンテンツを含む Web サイトへのアクセスをブロックし、すべてのドメインで Web アクティビティを追跡します。 [Web コンテンツ フィルターの設定に関するページを](#set-up-web-content-filtering)参照してください。 |
| **Microsoft Intune接続**<br/>(Intuneがある場合は、この設定を有効にすることをお勧めします) | 組織のサブスクリプションに Microsoft Intune ([Microsoft 365 Business Premium](../../business/index.yml)に含まれる) が含まれている場合、Defender for Business はデバイスに関する情報を Intune と共有できます。  |
| **デバイス検出**<br/>(既定でオンになっています) | セキュリティ チームが、会社のネットワークに接続されているアンマネージド デバイスを検索できるようにします。 不明なデバイスとアンマネージド デバイスは、パッチが適用されていないプリンター、セキュリティ構成が弱いネットワーク デバイス、セキュリティ制御のないサーバーなど、ネットワークに重大なリスクを生じます。<br/><br/>デバイス検出では、オンボードされたデバイスを使用してアンマネージド デバイスを検出するため、セキュリティ チームはアンマネージド デバイスをオンボードし、脆弱性を軽減できます。 <br/><br/>[デバイス検出の詳細については、こちらを参照してください](../defender-endpoint/device-discovery.md)。    |
| **プレビュー機能** | Microsoft では、Defender for Business などのサービスを継続的に更新し、新機能の機能強化と機能を追加しています。 プレビュー機能を受け取ることを選択した場合は、プレビュー エクスペリエンスで今後の機能を最初に試すことができます。 <br/><br/>[プレビュー機能の詳細については、こちらを参照してください](../defender-endpoint/preview.md)。  |

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで他の設定を表示および編集する

デバイスに適用されるセキュリティ ポリシーに加えて、Defender for Business で表示および編集できる他の設定もあります。 たとえば、使用するタイム ゾーンを指定したり、デバイスをオンボード (またはオフボード) したりできます。 

> [!NOTE]
> テナントには、この記事に記載されている設定よりも多くの設定が表示される場合があります。 この記事では、Defender for Business で確認する必要がある最も重要な設定について説明します。

### <a name="settings-to-review-for-defender-for-business"></a>Defender for Business を確認する設定

次の表では、Defender for Business で表示および編集できる設定について説明します。

| カテゴリ | Setting | 説明 |
|:---|:---|:---|
| **セキュリティ センター** | **タイム ゾーン** | インシデント、検出された脅威、自動調査と修復に表示される日付と時刻に使用するタイム ゾーンを選択します。 UTC またはローカル タイム ゾーンを使用できます (*推奨*)。  |
| **Microsoft 365 Defender** | **Account** | データの保存場所、テナント ID、組織 (組織) ID などの詳細を表示します。 |
| **Microsoft 365 Defender**  | **プレビュー機能**  | プレビュー機能を有効にして、今後の機能と新機能を試します。 最初に新機能をプレビューし、フィードバックを提供することができます。 |
| **エンドポイント**  | **メール通知** | 電子メール通知ルールを設定または編集します。 脆弱性が検出された場合、またはアラートが作成されると、電子メール通知ルールで指定された受信者に電子メールが送信されます。 [電子メール通知の詳細については、こちらを参照してください](mdb-email-notifications.md)。 |
| **エンドポイント**   | **デバイス管理** > **オンボーディング** | ダウンロード可能なスクリプトを使用して、デバイスを Defender for Business にオンボードします。 詳細については、「 [Defender for Business にデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。   |  
| **エンドポイント**  |  **デバイス管理** > **オフボード** | Defender for Business からデバイスをオフボード (削除) します。 デバイスをオフボードすると、Defender for Business にデータが送信されなくなりますが、オフボードの前に受信したデータは保持されます。 詳細については、「デバイスの [オフボード](mdb-offboard-devices.md)」を参照してください。  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで設定にアクセスする

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) に移動し、サインインします。

2. **[設定] を** 選択し、カテゴリ (**セキュリティ センター**、**Microsoft 365 Defender**、**エンドポイント** など) を選択します。

3. 設定の一覧で、表示または編集する項目を選択します。

## <a name="next-steps"></a>次の手順

- [Defender for Business の使用を開始する](mdb-get-started.md)
- [Defender for Business でデバイスを管理する](mdb-manage-devices.md)
- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business でポリシーを表示または編集する](mdb-view-edit-policies.md)
