---
title: Microsoft Defender for Business でセキュリティ設定を構成する
description: Microsoft Defender for Business でセキュリティ設定とポリシーを構成する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 18b259278f7f6053cdd7629eea114c3f61c82bb0
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61508349"
---
# <a name="configure-your-security-settings-and-policies-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business でセキュリティ設定とポリシーを構成する (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

会社のデバイスを Microsoft Defender for Business (プレビュー) にオンボードした後、次に、セキュリティ設定とポリシーを表示し、必要に応じて編集します。 

## <a name="what-to-do"></a>操作

1. [セキュリティ設定とポリシーを管理する場所を選択します](#choose-where-to-manage-security-settings-and-policies)。

2. [セキュリティ設定とポリシーを表示します](#view-your-security-settings-and-policies)。 

3. [次の手順に進みます](#next-steps)。

## <a name="choose-where-to-manage-security-settings-and-policies"></a>セキュリティ設定とポリシーを管理する場所を選択する

セキュリティ設定とポリシーの管理に関しては、次の表で説明するように、いくつかのオプションから選択できます。 <br/><br/>

| オプション | 説明 |
|:---|:---|
| **ポータルで既定のセキュリティ設定** とポリシーを使用する (推奨Microsoft 365 Defender) | Defender for Business (プレビュー) は、忙しい中小規模のビジネスを念頭に置いて設計されています。 Defender for Business の既定のセキュリティ設定とポリシーは、会社のデバイスを 1 日目から保護するように設計されています。<br/><br/>ポータル ( ) をMicrosoft 365 Defender [https://security.microsoft.com/](https://security.microsoft.com/) して、セキュリティ設定とポリシーを表示および管理できます。<br/><br/>詳細については、「デバイス ポリシーの [表示または編集」を参照してください](mdb-view-edit-policies.md)。 |
| **使用Microsoft エンドポイント マネージャー** | 会社がセキュリティ設定とポリシー Microsoft エンドポイント マネージャー使用している場合は、エンドポイント マネージャー を引き続き使用し、一部またはすべてのデバイスにセキュリティ ポリシーと設定を適用できます。 詳細については、「デバイス のセキュリティ[ポリシーを使用して](/mem/intune/protect/endpoint-security-policy)デバイス セキュリティを管理する」を参照Microsoft Intune。 <br/><br/>Defender for Business の簡略化 [された構成プロセスへの切り替えを検討してください](mdb-simplified-configuration.md)。 スイッチを切り替えた場合は、Microsoft エンドポイント マネージャー で既存のセキュリティ ポリシーを削除してから、Defender for Business の簡略化された構成プロセスに進む必要があります。 ポリシーを削除すると、Microsoft エンドポイント マネージャー後でポリシーの競合を回避できます。 |

> [!TIP]
> Microsoft Defender for Business プレビュー プログラムにサインアップする場合は、 を参照してください [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview) 。 詳細については [、「Get Microsoft Defender for Business (プレビュー)」を参照してください](get-defender-business.md)。

## <a name="view-your-security-settings-and-policies"></a>セキュリティ設定とポリシーを表示する

セキュリティ設定とポリシーを表示するには、次の表のいずれかの手順を使用します。
<br/><br/>

| portal | Procedure |
|:---|:---|
| Microsoft 365 Defender ポータル ( [https://security.microsoft.com](https://security.microsoft.com) ) | 1. ポータル ( ) のMicrosoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) し、サインインします。 <br/><br/>2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システムとポリシーの種類によって整理されます。<br/><br/>3. オペレーティング システム タブ (クライアントなど)**をWindowsします**。<br/><br/>4. カテゴリ (次世代保護や **ファイアウォールなど)** を展開して、ポリシーの一覧を表示します。<br/><br/>5. ポリシーを選択して、ポリシーの詳細を表示します。 ポリシー設定を変更したり、ポリシー設定の詳細を確認するには、次の記事を参照してください。 <br/>- [デバイス ポリシーの表示または編集](mdb-view-edit-policies.md)<br/>- [次世代の構成設定について](mdb-next-gen-configuration-settings.md)<br/>- [ファイアウォールの設定](mdb-firewall.md)  |
| Microsoft エンドポイント マネージャー管理センター ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) | 1. に移動 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) してサインインします。 これで、管理センター Microsoft エンドポイント マネージャーです。<br/><br/>2. [エンドポイント セキュリティ **] を選択します**。<br/><br/>3. ウイルス対策、ファイアウォール、**エンドポイント** の検出と応答、攻撃表面の縮小などのカテゴリを選択して、そのカテゴリのポリシーを表示します。 <br/><br/>セキュリティ設定の管理に関するヘルプを表示するには、Microsoft エンドポイント マネージャー でエンドポイント セキュリティの管理[から始Microsoft Intune。](/mem/intune/protect/endpoint-security) |

## <a name="next-steps"></a>次の手順

次のタスクの 1 つ以上に進みます。

- [Microsoft Defender for Business の使用を開始する (プレビュー)](mdb-get-started.md)

- [Microsoft Defender for Business でデバイスを管理する (プレビュー)](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business でポリシーを表示または編集する (プレビュー)](mdb-view-edit-policies.md)

