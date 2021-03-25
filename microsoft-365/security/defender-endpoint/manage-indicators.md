---
title: インジケーターの作成
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュ、IP アドレス、URL、またはドメインのインジケーターを作成します。
keywords: 管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a04f3be1f13fb57cd76cda7115d014f2ba3aa8d6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198827"
---
# <a name="create-indicators"></a>インジケーターの作成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

侵害の指標 (IoC) 照合は、すべてのエンドポイント保護ソリューションに不可欠な機能です。 この機能により、SecOps は検出およびブロック (予防と応答) のインジケーターの一覧を設定できます。

エンティティの検出、防止、除外を定義するインジケーターを作成します。 実行するアクションと、アクションを適用する期間、およびアクションを適用するデバイス グループの範囲を定義できます。

現在サポートされているソースは、Defender for Endpoint のクラウド検出エンジン、自動調査と修復エンジン、およびエンドポイント防止エンジン (Microsoft Defender Antivirus) です。

**クラウド検出エンジン**<br>
Defender for Endpoint のクラウド検出エンジンは、収集されたデータを定期的にスキャンし、設定したインジケーターの一致を試みます。 一致がある場合は、IoC に指定した設定に従ってアクションが実行されます。

**エンドポイント防止エンジン**<br>
インジケーターの同じリストは、予防エージェントによって受け入れされます。 つまり、Microsoft Defender AV がプライマリ AV 構成の場合、一致するインジケーターは設定に従って処理されます。 たとえば、アクションが "Alert and Block" の場合、Microsoft Defender AV はファイルの実行 (ブロックと修復) を防止し、対応するアラートが発生します。 一方、アクションが "許可" に設定されている場合、Microsoft Defender AV はファイルの実行を検出またはブロックします。

**自動調査と修復エンジン**<BR>
自動調査と修復は同じように動作します。 インジケーターが "許可" に設定されている場合、自動調査と修復は、そのインジケーターの "悪い" 評決を無視します。 "Block" に設定すると、自動調査と修復によって"悪い" と処理されます。


現在サポートされているアクションは次のとおりです。
- 許可
- アラートのみ
- アラートとブロック


次のインジケーターを作成できます。
- [Files](indicator-file.md)
- [IP アドレス、URL/ドメイン](indicator-ip-domain.md)
- [証明書](indicator-certificates.md)


> [!NOTE]
> テナントごとに 15,000 のインジケーターの制限があります。 ファイルと証明書のインジケーターは、Microsoft Defender ウイルス対策用に [定義された除外をブロックしない](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。 インジケーターは、Microsoft Defender ウイルス対策がパッシブ モードでサポートされていません。 


## <a name="related-topics"></a>関連項目

- [コンテキスト IoC の作成](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Microsoft Defender for Endpoint インジケーター API を使用する](ti-indicator.md)
- [パートナー統合ソリューションの使用](partner-applications.md)
