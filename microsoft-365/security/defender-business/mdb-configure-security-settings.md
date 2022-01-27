---
title: Microsoft Defender for Business でセキュリティ設定を構成する
description: Microsoft Defender for Business でセキュリティ設定とポリシーを構成する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/29/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365initiative-defender-business
ms.openlocfilehash: 7faefe829bc9ebdbc718e6c7ec370ceca612445a
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244597"
---
# <a name="configure-your-security-settings-and-policies-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business でセキュリティ設定とポリシーを構成する (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

会社のデバイスを Microsoft Defender for Business (プレビュー) にオンボードした後、次に、セキュリティ設定とポリシーを表示し、必要に応じて編集します。 Defender for Business (プレビュー) では、ポリシーを使用してデバイスにセキュリティ設定が適用されます。 これらのポリシーは、デバイス グループ [に適用されます](mdb-create-edit-device-groups.md#what-is-a-device-group)。 

Defender for Business (プレビュー) で構成できる他の設定もあります。 これらの設定には、タイム ゾーン、プレビュー機能を受け取るかどうかなどです。

## <a name="what-to-do"></a>操作

1. [Defender for Business の既定のセキュリティ ポリシーの概要を簡単に確認する](#default-policies-in-defender-for-business)

2. [セキュリティ ポリシーとデバイスを管理する場所を選択します](#choose-where-to-manage-security-policies-and-devices)。

3. [セキュリティ ポリシーを表示します](#view-your-security-policies)。

4. [ポータルで他の設定を表示およびMicrosoft 365 Defenderする](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal) 

5. [次の手順に進みます](#next-steps)。

## <a name="default-policies-in-defender-for-business"></a>Defender for Business の既定のポリシー

Defender for Business (プレビュー) には、推奨設定を使用する既定のポリシーが含まれています。 これらのポリシーには、次のものが含まれます。

- [脅威対策機能および](mdb-next-gen-configuration-settings.md)他の脅威保護機能Microsoft Defender ウイルス対策構成方法を決定する次世代の保護設定。 
- [会社の](mdb-firewall.md)クライアント デバイスとの間で流れるネットワーク トラフィックを決定するファイアウォールWindows設定。

初期セットアップ プロセス中に、既定のWindowsをクライアント デバイスに適用できます。 新しいポリシーを定義し、ビジネス ニーズに合わせて既存のポリシーを編集することもできます。 

## <a name="choose-where-to-manage-security-policies-and-devices"></a>セキュリティ ポリシーとデバイスを管理する場所を選択する

Defender for Business (プレビュー) は、セットアップ [と構成プロセス](mdb-simplified-configuration.md) の合理化に役立つ簡略化された構成プロセスを備しています。 簡略化された構成プロセスを選択した場合、セキュリティ ポリシーを表示および管理するには、Microsoft 365 Defenderポータル ( ) を使用します [https://security.microsoft.com/](https://security.microsoft.com/) 。 ただし、このオプションに限定されるわけではありません。 Microsoft エンドポイント マネージャー (Microsoft Intune を含む) または Microsoft 以外の生産性ソリューションを使用してセキュリティ ポリシーとデバイスを管理している場合は、現在のソリューションを使用し続けられます。

次の表は、セキュリティ ポリシーとデバイスを管理する場所を選択するのに役立ちます。 <br/><br/>

| オプション | 説明 |
|:---|:---|
| **ポータルで既定のセキュリティ設定** とポリシーを使用する (推奨Microsoft 365 Defender) | Defender for Business (プレビュー) は、忙しい中小規模のビジネスを念頭に置いて設計されています。 Defender for Business の既定のセキュリティ設定とポリシーは、会社のデバイスを 1 日目から保護するように設計されています。<br/><br/>ポータル ( ) をMicrosoft 365 Defender [https://security.microsoft.com/](https://security.microsoft.com/) して、セキュリティ設定とポリシーを表示および管理できます。<br/><br/>詳細については、「デバイス ポリシーの [表示または編集」を参照してください](mdb-view-edit-policies.md)。 |
| **使用Microsoft エンドポイント マネージャー** | 会社がセキュリティ設定とポリシー Microsoft エンドポイント マネージャー使用している場合は、エンドポイント マネージャー を引き続き使用し、一部またはすべてのデバイスにセキュリティ ポリシーと設定を適用できます。 詳細については、「デバイス のセキュリティ[ポリシーを使用して](/mem/intune/protect/endpoint-security-policy)デバイス セキュリティを管理する」を参照Microsoft Intune。 <br/><br/>Defender for Business の簡略化 [された構成プロセスへの切り替えを検討してください](mdb-simplified-configuration.md)。 スイッチを切り替えた場合は、Microsoft エンドポイント マネージャー で既存のセキュリティ ポリシーを削除してから、Defender for Business の簡略化された構成プロセスに進む必要があります。 ポリシーを削除すると、Microsoft エンドポイント マネージャー後でポリシーの競合を回避できます。 |

> [!TIP]
> Microsoft Defender for Business プレビュー プログラムにサインアップする場合は、 を参照してください [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview) 。 詳細については [、「Get Microsoft Defender for Business (プレビュー)」を参照してください](get-defender-business.md)。

## <a name="view-your-security-policies"></a>セキュリティ ポリシーの表示

セキュリティ ポリシーの一覧を表示するには、次の表のいずれかの手順を使用します。
<br/><br/>

| portal | Procedure |
|:---|:---|
| Microsoft 365 Defender ポータル ( [https://security.microsoft.com](https://security.microsoft.com) ) | 1. ポータル ( ) のMicrosoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) し、サインインします。 <br/><br/>2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システムとポリシーの種類によって整理されます。<br/><br/>3. オペレーティング システム タブ (クライアントなど)**をWindowsします**。<br/><br/>4. カテゴリ (次世代保護や **ファイアウォールなど)** を展開して、ポリシーの一覧を表示します。<br/><br/>5. ポリシーを選択して、ポリシーの詳細を表示します。 ポリシー設定を変更したり、ポリシー設定の詳細を確認するには、次の記事を参照してください。 <br/>- [デバイス ポリシーの表示または編集](mdb-view-edit-policies.md)<br/>- [次世代の構成設定について](mdb-next-gen-configuration-settings.md)<br/>- [ファイアウォールの設定](mdb-firewall.md)  |
| Microsoft エンドポイント マネージャー管理センター ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) | 1. に移動 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) してサインインします。 これで、管理センター Microsoft エンドポイント マネージャーです。<br/><br/>2. [エンドポイント セキュリティ **] を選択します**。<br/><br/>3. ウイルス対策、ファイアウォール、**エンドポイント** の検出と応答、攻撃表面の縮小などのカテゴリを選択して、そのカテゴリのポリシーを表示します。 <br/><br/>セキュリティ設定の管理に関するヘルプを表示するには、Microsoft エンドポイント マネージャー でエンドポイント セキュリティの管理[から始Microsoft Intune。](/mem/intune/protect/endpoint-security) |

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>ポータルで他の設定を表示およびMicrosoft 365 Defenderする

デバイスに適用されるセキュリティ ポリシーに加えて、Defender for Business (プレビュー) で表示および編集できる他の設定があります。 たとえば、使用するタイム ゾーンを指定し、デバイスをオンボード (またはオフボード) できます。 

> [!NOTE]
> テナントには、この記事に記載されている設定よりも多くの設定が表示される場合があります。 Defender for Business (プレビュー) で確認する必要がある設定を強調表示しています。

### <a name="settings-to-review-for-defender-for-business"></a>設定 Defender for Business のレビューする方法

次の表では、Defender for Business (プレビュー) で表示 (および必要に応じて編集) する設定について説明します。

<br/><br/>

| カテゴリ | Setting | 説明 |
|:---|:---|:---|
| **セキュリティ センター** | **タイム ゾーン** | インシデント、検出された脅威、および自動調査に表示される日付と時刻に使用するタイム ゾーンを選択し、修復&します。 UTC またはローカル タイム ゾーン (推奨) を使用 *できます*。  |
| **Microsoft 365 Defender** | **Account** | データの保存場所、テナント ID、会社 (組織) ID などの詳細を表示します。 |
| **Microsoft 365 Defender**  | **プレビュー機能**  | プレビュー機能を有効にし、今後の機能と新機能を試します。 最初に新機能をプレビューし、フィードバックを提供することができます。 |
| **エンドポイント**  | **電子メール通知** | 電子メール通知ルールを設定または編集します。 脆弱性が検出された場合、またはアラートが作成されると、電子メール通知ルールで指定された受信者が電子メールを受信します。 [メール通知の詳細については、次の情報を参照してください](mdb-email-notifications.md)。 |
| **エンドポイント**   | **デバイスの管理**  > **オンボーディング** | ダウンロード可能なスクリプトを使用して、デバイスを Defender for Business にオンボードします。 詳細については [、「Defender for Business でローカル スクリプトを使用してデバイスをオンボードする」を参照してください](mdb-onboard-devices.md#onboard-a-device-using-a-local-script-in-defender-for-business)。   |  
| **エンドポイント**  |  **デバイスの管理**  > **オフボード** | Defender for Business (プレビュー) からオフボード (削除) デバイス。 デバイスをオフボードすると、Defender for Business (プレビュー) にデータが送信されなくなりましたが、オフボード前に受信したデータは保持されます。 詳細については [、「Offboard a device」を参照してください](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device)。  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>ポータルで設定にMicrosoft 365 Defenderする

1. ポータル ( ) にMicrosoft 365 Defender [https://security.microsoft.com/](https://security.microsoft.com/) し、サインインします。

2. **[設定]** を選択し、カテゴリ (セキュリティセンター、セキュリティ センター、Microsoft 365 Defenderエンドポイント **など) を****選択します**。

3. 設定の一覧で、表示または編集するアイテムを選択します。


## <a name="next-steps"></a>次の手順

次のタスクの 1 つ以上に進みます。

- [Microsoft Defender for Business の使用を開始する (プレビュー)](mdb-get-started.md)

- [Microsoft Defender for Business でデバイスを管理する (プレビュー)](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business でポリシーを表示または編集する (プレビュー)](mdb-view-edit-policies.md)

