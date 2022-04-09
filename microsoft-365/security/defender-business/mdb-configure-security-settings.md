---
title: Microsoft Defender for Businessでセキュリティ設定を表示および編集する
description: Microsoft Defender for Businessでセキュリティ ポリシーを構成する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 3d6ef3a7bc3ae9b7556041cedc88df354421f885
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746494"
---
# <a name="view-and-edit-your-security-policies-and-settings-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでセキュリティ ポリシーと設定を表示および編集する

> [!IMPORTANT]
> Microsoft Defender for Businessは、2022 年 3 月 1 日以降、[Microsoft 365 Business Premium](../../business-premium/index.md)のお客様に展開されます。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー段階にあり、 [ここにサインアップ](https://aka.ms/mdb-preview) して要求する顧客と IT パートナーに段階的にロールアウトされます。 プレビューには [シナリオの初期セット](mdb-tutorials.md#try-these-preview-scenarios)が含まれており、定期的に機能を追加します。
> 
> この記事の一部の情報は、市販される前に大幅に変更される可能性があるプレリリースされた製品/サービスに関連しています。 Microsoft は、ここに記載されている情報に対して、明示的または黙示的な保証を行いません。 

## <a name="overview"></a>概要

会社のデバイスをMicrosoft Defender for Businessにオンボードしたら、次の手順ではセキュリティ ポリシーと設定を表示し、必要に応じて編集します。 構成するセキュリティ ポリシーは次のとおりです。

- 会社のデバイスのウイルス対策とマルウェア対策の保護を決定する **[次世代保護ポリシー](#view-or-edit-your-next-generation-protection-policies)**
- **[ファイアウォールの保護とルール](#view-or-edit-your-firewall-policies-and-custom-rules)**。会社のデバイスとの間で送受信できるネットワーク トラフィックを決定します
- **[Web コンテンツ フィルター。](#set-up-web-content-filtering)** 成人コンテンツや法的責任などのカテゴリに基づいて特定の Web サイト (URL) にアクセスできないようにします。

Defender for Business では、デバイス [グループ](mdb-create-edit-device-groups.md#what-is-a-device-group)を介してデバイスにセキュリティ ポリシーが適用されます。 

セキュリティ ポリシーに加えて、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で使用するタイム ゾーンや、プレビュー機能が使用可能になった時点で受信するかどうかなどの[設定を表示および編集](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)できます。

この記事は、セキュリティ ポリシーと設定を管理するためのガイドとして使用します。

## <a name="what-to-do"></a>操作

1. [セキュリティ ポリシーとデバイスを管理する場所を選択します](#choose-where-to-manage-security-policies-and-devices)。

2. [次世代の保護ポリシーを表示または編集します](#view-or-edit-your-next-generation-protection-policies)。

3. [ファイアウォール ポリシーとカスタム ルールを表示または編集](#view-or-edit-your-firewall-policies-and-custom-rules)します。

4. [Web コンテンツ フィルターを設定します](#set-up-web-content-filtering)。

5. [Microsoft 365 Defender ポータルで他の設定を表示および編集します](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)。 

6. [次の手順に進みます](#next-steps)。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Businessに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="choose-where-to-manage-security-policies-and-devices"></a>セキュリティ ポリシーとデバイスを管理する場所を選択する

Defender for Business は、セットアップと構成プロセスを効率化するのに役立つ [簡略化された](mdb-simplified-configuration.md) 構成プロセスを備えています。 簡略化された構成プロセスを選択した場合は、Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) でセキュリティ ポリシーを表示および管理できます。 ただし、このオプションに限定されるわけではありません。 Microsoft エンドポイント マネージャー (Microsoft Intuneを含む) を使用している場合は、エンドポイント マネージャーを使用し続けることができます。

次の表は、セキュリティ ポリシーとデバイスを管理する場所を選択するのに役立ちます。 <br/><br/>

| オプション | 説明 |
|:---|:---|
| **Microsoft 365 Defender ポータルを使用** する (*推奨*) | Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) は、会社のデバイス、セキュリティ ポリシー、およびセキュリティ設定を管理するためのワンストップ ショップです。 セキュリティ ポリシーと設定にアクセスし、 [脅威&脆弱性管理ダッシュボード](mdb-view-tvm-dashboard.md)を使用し、インシデントをすべて 1 か所で [表示および管理](mdb-view-manage-incidents.md) できます。 <br/><br/>Microsoft エンドポイント マネージャーを使用している場合は、Defender for Business にオンボードしたデバイスとセキュリティ ポリシーがエンドポイント マネージャーに表示されます。 詳細については、次の記事を参照してください。<br/><br/>- [Defender for Business の既定の設定とMicrosoft エンドポイント マネージャー](mdb-next-gen-configuration-settings.md#defender-for-business-default-settings-and-microsoft-endpoint-manager)<br/><br/>- [Microsoft Defender for Businessのファイアウォール](mdb-firewall.md)   |
| **Microsoft エンドポイント マネージャーを使用する** | 会社が既に エンドポイント マネージャー (Microsoft Intuneを含む) を使用してセキュリティ ポリシーを管理している場合は、エンドポイント マネージャーを使用してデバイスとセキュリティ ポリシーを管理し続けることができます。 詳細については、「Microsoft Intuneの[エンドポイント セキュリティ ポリシーを使用したデバイス セキュリティの管理](/mem/intune/protect/endpoint-security-policy)」を参照してください。 <br/><br/>[Defender for Business で簡略化された構成プロセス](mdb-simplified-configuration.md)に切り替える場合は、後でポリシーの[競合](mdb-troubleshooting.yml)を回避するために、エンドポイント マネージャー内の既存のセキュリティ ポリシーをすべて削除するように求められます。 |

> [!IMPORTANT]
> Microsoft 365 Defender ポータルでセキュリティ ポリシーを管理している場合は、ウイルス対策ポリシーまたはファイアウォール ポリシーとして一覧表示されているエンドポイント マネージャーで、これらのポリシーを *表示* できます。 エンドポイント マネージャーでファイアウォール ポリシーを表示すると、ファイアウォール保護用のポリシーとカスタム ルール用のポリシーの 2 つのポリシーが一覧表示されます。

## <a name="view-or-edit-your-next-generation-protection-policies"></a>次世代の保護ポリシーを表示または編集する

Microsoft 365 Defender ポータルを使用しているか、Microsoft エンドポイント マネージャーを使用して次世代保護ポリシーを管理しているかに応じて、次の表のいずれかの手順を使用します。 <br/><br/>

| portal | プロシージャ |
|:---|:---|
| Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 <br/><br/>2. ナビゲーション ウィンドウで、[ **デバイスの構成**] を選択します。 ポリシーは、オペレーティング システムとポリシーの種類によって編成されます。<br/><br/>3. オペレーティング システム タブ (**Windows クライアント** など) を選択します。<br/><br/>4. **次世代保護を** 展開して、ポリシーの一覧を表示します。<br/><br/>5. ポリシーを選択して、ポリシーの詳細を表示します。 変更を加えたり、ポリシー設定の詳細を確認したりするには、次の記事を参照してください。 <br/>- [デバイス ポリシーを表示または編集する](mdb-view-edit-policies.md)<br/>- [次世代の構成設定を理解する](mdb-next-gen-configuration-settings.md)  |
| Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. に移動して [https://endpoint.microsoft.com](https://endpoint.microsoft.com) サインインします。 これで、Microsoft エンドポイント マネージャー管理センターに入るようになりました。<br/><br/>2. **[エンドポイント セキュリティ] を選択します**。<br/><br/>3. **[ウイルス対策]** を選択して、そのカテゴリのポリシーを表示します。 <br/><br/>Microsoft エンドポイント マネージャーのセキュリティ設定の管理に関するヘルプを表示するには、Microsoft Intune[のエンドポイント セキュリティの管理から](/mem/intune/protect/endpoint-security)始めます。 |

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>ファイアウォール ポリシーとカスタム ルールを表示または編集する

Microsoft 365 Defender ポータルまたはMicrosoft エンドポイント マネージャーを使用してファイアウォール保護を管理しているかに応じて、次の表のいずれかの手順を使用します。 <br/><br/>

| portal | プロシージャ |
|:---|:---|
| Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 <br/><br/>2. ナビゲーション ウィンドウで、[ **デバイスの構成**] を選択します。 ポリシーは、オペレーティング システムとポリシーの種類によって編成されます。<br/><br/>3. オペレーティング システム タブ (**Windows クライアント** など) を選択します。<br/><br/>4. **ファイアウォール** を展開して、ポリシーの一覧を表示します。<br/><br/>5. ポリシーを選択して、ポリシーの詳細を表示します。 変更を加えたり、ポリシー設定の詳細を確認したりするには、次の記事を参照してください。 <br/>- [デバイス ポリシーを表示または編集する](mdb-view-edit-policies.md)<br/>- [ファイアウォールの設定](mdb-firewall.md)<br/>- [ファイアウォール ポリシーのカスタム ルールを管理する](mdb-custom-rules-firewall.md)  |
| Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. に移動して [https://endpoint.microsoft.com](https://endpoint.microsoft.com) サインインします。 これで、Microsoft エンドポイント マネージャー管理センターに入るようになりました。<br/><br/>2. **[エンドポイント セキュリティ] を選択します**。<br/><br/>3. **[ファイアウォール** ] を選択して、そのカテゴリのポリシーを表示します。 ファイアウォール保護用に定義されたカスタム規則は、個別のポリシーとして一覧表示されます。<br/><br/>Microsoft エンドポイント マネージャーのセキュリティ設定の管理に関するヘルプを表示するには、Microsoft Intune[のエンドポイント セキュリティの管理から](/mem/intune/protect/endpoint-security)始めます。 |

## <a name="set-up-web-content-filtering"></a>Web コンテンツ フィルターを設定する

Web コンテンツ フィルターを使用すると、セキュリティ チームは、次のようなコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。

- 成人向けコンテンツ: カルト、賭け行為、ヌード、ポルノ、性的に明示的な資料、または暴力に関連するサイト

- 高帯域幅: サイト、イメージ共有サイト、またはピアツーピア ホストをダウンロードする

- 法的責任: 児童の不正使用画像を含むサイト、違法な行為の促進、盗用または学校の不正行為を促進するサイト、または有害な活動を促進するサイト

- 娯楽: Web ベースのチャット ルーム、オンライン ゲーム、Web ベースの電子メール、ソーシャル ネットワークを提供するサイト

- 分類されていない: コンテンツがないサイト、または新しく登録されたサイト

これらのカテゴリのすべての Web サイトが悪意のあるわけではありませんが、コンプライアンス規制、帯域幅の使用、またはその他の懸念があるため、会社にとって問題になる可能性があります。 さらに、監査専用ポリシーを作成して、セキュリティ チームが Web サイトカテゴリをブロックする必要があるかどうかをよりよく理解することができます。

Web コンテンツ フィルターは、主要な Web ブラウザーで使用できます。Windows Defender SmartScreen (Microsoft Edge) と Network Protection (Chrome、Firefox、Brave、Opera) によって実行されるブロックがあります。 詳細については、「 [Web コンテンツ フィルターの前提条件」](../defender-endpoint/web-content-filtering.md#prerequisites)を参照してください。

### <a name="to-set-up-web-content-filtering"></a>Web コンテンツ フィルターを設定するには

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、**設定** > **Web コンテンツ フィルター** **+ ポリシーの追加** を > 選択します。

2. ポリシーの名前と説明を指定します。

3. ブロックするカテゴリを選択します。 展開アイコンを使用して、各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。

   Web サイトをブロックしない監査専用ポリシーを設定するには、カテゴリを選択しないでください。

   **[Uncategorized]** を選択しないでください。

4. ポリシーを適用するデバイス グループを選択して、ポリシー スコープを指定します。 選択したデバイス グループ内のデバイスのみが、選択したカテゴリの Web サイトにアクセスできなくなります。

5. 概要を確認し、ポリシーを保存します。 ポリシーの更新は、選択したデバイスに適用されるまでに最大 2 時間かかる場合があります。

> [!TIP]
> Web コンテンツ のフィルター処理の詳細については、「 [Web コンテンツ のフィルター処理](../defender-endpoint/web-content-filtering.md)」を参照してください。

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで他の設定を表示および編集する

デバイスに適用されるセキュリティ ポリシーに加えて、Defender for Business で表示および編集できる他の設定もあります。 たとえば、使用するタイム ゾーンを指定すると、デバイスをオンボード (またはオフボード) できます。 

> [!NOTE]
> テナントには、この記事に記載されている設定よりも多くの設定が表示される場合があります。 この記事では、Defender for Business で確認する必要がある最も重要な設定について説明します。

### <a name="settings-to-review-for-defender-for-business"></a>Defender for Business を確認する設定

次の表では、Defender for Business で表示 (および必要に応じて編集) する設定について説明します。

<br/><br/>

| カテゴリ | 設定 | 説明 |
|:---|:---|:---|
| **セキュリティ センター** | **タイム ゾーン** | インシデント、検出された脅威、および自動調査&修復に表示される日付と時刻に使用するタイム ゾーンを選択します。 UTC またはローカル タイム ゾーンを使用できます (*推奨*)。  |
| **Microsoft 365 Defender** | **Account** | データの格納場所、テナント ID、組織 (組織) ID など、詳細を表示します。 |
| **Microsoft 365 Defender**  | **プレビュー機能**  | プレビュー機能を有効にして、今後の機能と新機能を試します。 最初に新機能をプレビューし、フィードバックを提供することができます。 |
| **エンドポイント**  | **メール通知** | 電子メール通知ルールを設定または編集します。 脆弱性が検出された場合、またはアラートが作成されると、電子メール通知ルールで指定された受信者に電子メールが送信されます。 [電子メール通知の詳細については、こちらを参照してください](mdb-email-notifications.md)。 |
| **エンドポイント**   | **デバイス管理** > **オンボーディング** | ダウンロード可能なスクリプトを使用して、デバイスを Defender for Business にオンボードします。 詳細については、「[デバイスをMicrosoft Defender for Businessにオンボードする](mdb-onboard-devices.md)」を参照してください。   |  
| **エンドポイント**  |  **デバイス管理** > **オフボード** | Defender for Business からデバイスをオフボード (削除) します。 デバイスをオフボードすると、Defender for Business にデータが送信されなくなりますが、オフボードの前に受信したデータは保持されます。 詳細については、「デバイスの [オフボード](mdb-onboard-devices.md#offboarding-a-device)」を参照してください。  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで設定にアクセスする

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com/](https://security.microsoft.com/)) に移動し、サインインします。

2. **設定** を選択し、カテゴリ (**セキュリティ センター**、**Microsoft 365 Defender**、**エンドポイント** など) を選択します。

3. 設定の一覧で、表示または編集する項目を選択します。


## <a name="next-steps"></a>次のステップ

次のタスクの 1 つ以上に進みます。

- [Microsoft Defender for Businessを使用した概要](mdb-get-started.md)
- [Microsoft Defender for Businessでデバイスを管理する](mdb-manage-devices.md)
- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)
- [Microsoft Defender for Businessでポリシーを表示または編集する](mdb-view-edit-policies.md)
