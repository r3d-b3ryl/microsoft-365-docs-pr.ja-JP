---
title: Microsoft Defender for Business でセキュリティ設定を表示および編集する
description: Microsoft Defender for Business でセキュリティ ポリシーを構成する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/14/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 5673ac38577dbd87019a954eb388d6ab8f050328
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504756"
---
# <a name="view-and-edit-your-security-policies-and-settings-in-microsoft-defender-for-business"></a>Microsoft Defender for Business でセキュリティ ポリシーと設定を表示および編集する

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。[](../../business-premium/index.md) スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

## <a name="overview"></a>概要

組織のデバイスを Microsoft Defender for Business にオンボードした後、次にセキュリティ ポリシーと設定を表示し、必要に応じて編集します。 セキュリティ ポリシーには、次のものが含まれます。

- **[組織のデバイスに](#view-or-edit-your-next-generation-protection-policies)** 対するウイルス対策とマルウェア対策の保護を決定する次世代の保護ポリシー

- **[ファイアウォールの保護とルール](#view-or-edit-your-firewall-policies-and-custom-rules)**。組織のデバイスに対して、または組織のデバイスから流れるネットワーク トラフィックを決定する

- **[成人向け](#set-up-web-content-filtering)** コンテンツや法的責任などのカテゴリに基づいて特定の Web サイト (URL) にアクセスできない Web コンテンツ フィルター。

Defender for Business では、セキュリティ ポリシーはデバイス グループを介してデバイスに [適用されます](mdb-create-edit-device-groups.md#what-is-a-device-group)。 

セキュリティ ポリシーに加えて、Microsoft 365 Defender ポータルで使用[](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)するタイム ゾーン ([https://security.microsoft.com](https://security.microsoft.com))、利用可能になったプレビュー機能を受け取るかどうかなどの設定を表示および編集できます。

この記事は、セキュリティ ポリシーと設定を管理するためのガイドとして使用します。

## <a name="what-to-do"></a>操作

1. [セキュリティ ポリシーとデバイスを管理する場所を選択します](#choose-where-to-manage-security-policies-and-devices)。

2. [次世代の保護ポリシーを表示または編集します](#view-or-edit-your-next-generation-protection-policies)。

3. [ファイアウォール ポリシーとカスタム ルールを表示または編集します](#view-or-edit-your-firewall-policies-and-custom-rules)。

4. [Web コンテンツ フィルターを設定します](#set-up-web-content-filtering)。

5. [ポータルで他の設定を表示およびMicrosoft 365 Defenderします](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal)。 

6. [次の手順に進みます](#next-steps)。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="choose-where-to-manage-security-policies-and-devices"></a>セキュリティ ポリシーとデバイスを管理する場所を選択する

Defender for Business では、 [セットアップと構成プロセスを](mdb-simplified-configuration.md) 合理化する簡略化された構成プロセスが機能します。 簡略化された構成プロセスを選択した場合は、セキュリティ ポリシーを表示および管理できます () Microsoft 365 Defenderできます[https://security.microsoft.com/](https://security.microsoft.com/)。 ただし、このオプションに限定されるわけではありません。 (この機能を含む) Microsoft エンドポイント マネージャーを使用しているMicrosoft Intune、ユーザー設定を使用エンドポイント マネージャー。

次の表は、セキュリティ ポリシーとデバイスを管理する場所を選択するのに役立ちます。 <br/><br/>

| オプション | 説明 |
|:---|:---|
| **ポータルをMicrosoft 365 Defenderする** (*推奨*) | このMicrosoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) は、組織のデバイス、セキュリティ ポリシー、およびセキュリティ設定を管理するためのワンストップ ショップです。 セキュリティ ポリシーと設定にアクセスし、Threat [&](mdb-view-tvm-dashboard.md) の脆弱性管理ダッシュボードを使用し、インシデントの表示と[](mdb-view-manage-incidents.md)管理を 1 か所で行えます。 <br/><br/>セキュリティ ポリシーを使用しているMicrosoft エンドポイント マネージャー、Defender for Business にオンボードしたデバイスとセキュリティ ポリシーは、そのデバイスにエンドポイント マネージャー。 詳細については、次の記事を参照してください。<br/><br/>- [Defender for Business の既定の設定とMicrosoft エンドポイント マネージャー](mdb-next-gen-configuration-settings.md#defender-for-business-default-settings-and-microsoft-endpoint-manager)<br/><br/>- [ビジネス向け Microsoft Defender のファイアウォール](mdb-firewall.md)   |
| **使用Microsoft エンドポイント マネージャー** | 組織でセキュリティ ポリシーの管理に エンドポイント マネージャー (Microsoft Intune を含む) を既に使用している場合は、エンドポイント マネージャー を使用してデバイスとセキュリティ ポリシーを管理できます。 詳細については、「エンドポイント セキュリティ ポリシー[を使用](/mem/intune/protect/endpoint-security-policy)してデバイス セキュリティを管理する」を参照Microsoft Intune。 <br/><br/>[Defender for Business](mdb-simplified-configuration.md) の簡略化された構成プロセスに切り替える場合は、エンドポイント マネージャー で既存のセキュリティ ポリシーを削除して、後でポリシーの競合を回避するように求めるメッセージ[](mdb-troubleshooting.yml)が表示されます。 |

> [!IMPORTANT]
> Microsoft 365 Defender ポータルでセキュリティ ポリシーを管理している場合は、ウイルス対策ポリシーまたはファイアウォール ポリシーとしてエンドポイント マネージャーでこれらのポリシーを表示できます。 ファイアウォール ポリシーを エンドポイント マネージャー で表示すると、ファイアウォール保護のポリシーとカスタム ルールの 2 つのポリシーが表示されます。

## <a name="view-or-edit-your-next-generation-protection-policies"></a>次世代の保護ポリシーを表示または編集する

Microsoft 365 Defender ポータルまたは Microsoft エンドポイント マネージャー を使用して次世代の保護ポリシーを管理するかどうかに応じて、次の表のいずれかの手順を使用します。 <br/><br/>

| portal | Procedure |
|:---|:---|
| Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) | 1. ポータル () のMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。 <br/><br/>2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システムとポリシーの種類によって整理されます。<br/><br/>3. オペレーティング システム タブ (クライアントなど) **をWindowsします**。<br/><br/>4. [次世代 **の保護] を展開** して、ポリシーの一覧を表示します。<br/><br/>5. ポリシーを選択して、ポリシーの詳細を表示します。 ポリシー設定を変更したり、ポリシー設定の詳細を確認するには、次の記事を参照してください。 <br/>- [デバイス ポリシーの表示または編集](mdb-view-edit-policies.md)<br/>- [次世代の構成設定について](mdb-next-gen-configuration-settings.md)  |
| Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. に移動して [https://endpoint.microsoft.com](https://endpoint.microsoft.com) サインインします。 これで、管理センター Microsoft エンドポイント マネージャーされます。<br/><br/>2. [エンドポイント セキュリティ **] を選択します**。<br/><br/>3. [ **ウイルス対策] を** 選択して、そのカテゴリのポリシーを表示します。 <br/><br/>セキュリティ設定の管理に関するヘルプを表示するには、Microsoft エンドポイント マネージャーでエンドポイント セキュリティの管理[から始Microsoft Intune](/mem/intune/protect/endpoint-security)。 |

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>ファイアウォール ポリシーとカスタム ルールを表示または編集する

Microsoft 365 Defender ポータルまたは Microsoft エンドポイント マネージャー を使用してファイアウォール保護を管理するかどうかに応じて、次の表のいずれかの手順を使用します。 <br/><br/>

| portal | Procedure |
|:---|:---|
| Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) | 1. ポータル () のMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。 <br/><br/>2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システムとポリシーの種類によって整理されます。<br/><br/>3. オペレーティング システム タブ (クライアントなど) **をWindowsします**。<br/><br/>4. [ **ファイアウォール] を展開** してポリシーの一覧を表示します。<br/><br/>5. ポリシーを選択して、ポリシーの詳細を表示します。 ポリシー設定を変更したり、ポリシー設定の詳細を確認するには、次の記事を参照してください。 <br/>- [デバイス ポリシーの表示または編集](mdb-view-edit-policies.md)<br/>- [ファイアウォールの設定](mdb-firewall.md)<br/>- [ファイアウォール ポリシーのカスタム ルールを管理する](mdb-custom-rules-firewall.md)  |
| Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. に移動して [https://endpoint.microsoft.com](https://endpoint.microsoft.com) サインインします。 これで、管理センター Microsoft エンドポイント マネージャーされます。<br/><br/>2. [エンドポイント セキュリティ **] を選択します**。<br/><br/>3. [ **ファイアウォール] を** 選択して、そのカテゴリのポリシーを表示します。 ファイアウォール保護用に定義されたカスタム ルールは、個別のポリシーとして一覧表示されます。<br/><br/>セキュリティ設定の管理に関するヘルプを表示するには、Microsoft エンドポイント マネージャーでエンドポイント セキュリティの管理[から始Microsoft Intune](/mem/intune/protect/endpoint-security)。 |

## <a name="set-up-web-content-filtering"></a>Web コンテンツ フィルターの設定

Web コンテンツ フィルターを使用すると、セキュリティ チームは、次のようなコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。

- アダルト コンテンツ: カルト、ギャンブル、ヌード、ビデオ、性的に明示的な資料、または暴力に関連するサイト

- 高帯域幅: サイト、イメージ共有サイト、ピアツーピア ホストをダウンロードする

- 法的責任: 児童虐待画像を含むサイト、違法行為の促進、盗作や学校の不正行為の促進、または有害な活動を促進するサイト

- レジャー: Web ベースのチャット ルーム、オンライン ゲーム、Web ベースの電子メール、またはソーシャル ネットワーキングを提供するサイト

- 未分類: コンテンツがないサイト、または新しく登録されたサイト

これらのカテゴリのすべての Web サイトが悪意のあるとは限りませんが、コンプライアンス規制、帯域幅の使用、その他の懸念により、組織にとって問題になる可能性があります。 さらに、監査専用ポリシーを作成して、セキュリティ チームが Web サイト のカテゴリをブロックするかどうかを理解することもできます。

Web コンテンツ フィルターは主要な Web ブラウザーで利用できます。ブロックは Windows Defender SmartScreen (Microsoft Edge) とネットワーク保護 (Chrome、Firefox、Brave、および Opera) によって実行されます。 詳細については、「Web コンテンツ フィルター [の前提条件」を参照してください](../defender-endpoint/web-content-filtering.md#prerequisites)。

### <a name="to-set-up-web-content-filtering"></a>Web コンテンツ フィルターを設定するには

1. [Web コンテンツ Microsoft 365 Defender ] ([https://security.microsoft.com](https://security.microsoft.com)) で、[Web **コンテンツ フィルター設定** > **ポリシー** > の追加 **] を選択します**。

2. ポリシーの名前と説明を指定します。

3. ブロックするカテゴリを選択します。 展開アイコンを使用して、各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。

   Web サイトをブロックしない監査専用ポリシーを設定するには、カテゴリを選択しない必要があります。

   [未分類 **] を選択しない**。

4. ポリシーを適用するデバイス グループを選択して、ポリシースコープを指定します。 選択したデバイス グループ内のデバイスだけが、選択したカテゴリの Web サイトにアクセスできません。

5. 概要を確認し、ポリシーを保存します。 ポリシーの更新には、選択したデバイスに適用するために最大 2 時間かかる場合があります。

> [!TIP]
> Web コンテンツ フィルターの詳細については、「Web コンテンツ フィルター [」を参照してください](../defender-endpoint/web-content-filtering.md)。

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>ポータルで他の設定を表示およびMicrosoft 365 Defenderする

デバイスに適用されるセキュリティ ポリシーに加えて、Defender for Business で表示および編集できる他の設定があります。 たとえば、使用するタイム ゾーンを指定し、デバイスをオンボード (またはオフボード) できます。 

> [!NOTE]
> テナントには、この記事に記載されている設定よりも多くの設定が表示される場合があります。 この記事では、Defender for Business で確認する必要がある最も重要な設定について強調します。

### <a name="settings-to-review-for-defender-for-business"></a>設定のレビューする方法

次の表では、Defender for Business で表示 (および必要に応じて編集) する設定について説明します。

<br/><br/>

| カテゴリ | Setting | 説明 |
|:---|:---|:---|
| **セキュリティ センター** | **タイム ゾーン** | インシデント、検出された脅威、および自動調査に表示される日付と時刻に使用するタイム ゾーンを選択し、修復&します。 UTC またはローカル タイム ゾーン (推奨) を使用 *できます*。  |
| **Microsoft 365 Defender** | **Account** | データの保存場所、テナント ID、組織 (組織) ID などの詳細を表示します。 |
| **Microsoft 365 Defender**  | **プレビュー機能**  | プレビュー機能を有効にし、今後の機能と新機能を試します。 最初に新機能をプレビューし、フィードバックを提供することができます。 |
| **エンドポイント**  | **電子メール通知** | 電子メール通知ルールを設定または編集します。 脆弱性が検出された場合、またはアラートが作成されると、電子メール通知ルールで指定された受信者が電子メールを受信します。 [電子メール通知の詳細については、次の情報を参照してください](mdb-email-notifications.md)。 |
| **エンドポイント**   | **デバイスの管理** > **オンボーディング** | ダウンロード可能なスクリプトを使用して、デバイスを Defender for Business にオンボードします。 詳細については、「オンボード デバイス [から Microsoft Defender for Business」を参照してください](mdb-onboard-devices.md)。   |  
| **エンドポイント**  |  **デバイスの管理** > **オフボード** | Defender for Business からオフボード (削除) デバイス。 デバイスをオフボードすると、デバイスは Defender for Business にデータを送信しなくなりましたが、オフボード前に受信したデータは保持されます。 詳細については、「 [Offboarding a device」を参照してください](mdb-onboard-devices.md#offboarding-a-device)。  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>ポータルで設定にMicrosoft 365 Defenderする

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com/](https://security.microsoft.com/)、サインインします。

2. [**設定**] を選択し、カテゴリ (セキュリティ センター、セキュリティ センター、Microsoft 365 Defenderエンドポイントなど) **を****選択します**。

3. 設定の一覧で、表示または編集するアイテムを選択します。


## <a name="next-steps"></a>次の手順

次のタスクの 1 つ以上に進みます。

- [Microsoft Defender for Business の使用を開始する](mdb-get-started.md)

- [Microsoft Defender for Business でデバイスを管理する](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business でポリシーを表示または編集する](mdb-view-edit-policies.md)
