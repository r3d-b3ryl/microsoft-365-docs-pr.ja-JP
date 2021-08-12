---
title: インジケーターの作成
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュ、IP アドレス、URL、またはドメインのインジケーターを作成します。
keywords: 管理、許可、ブロックされた、ブロック、クリーン、悪意のある、ファイル ハッシュ、ip アドレス、URL、ドメイン
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
ms.openlocfilehash: a015755d0848b0287854db67021599917851d889bb178ff4f4129e02c09919db
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53806302"
---
# <a name="create-indicators"></a>インジケーターの作成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

侵害インジケーター (IoCs) マッチングは、すべてのエンドポイント保護ソリューションで不可欠な機能です。 この機能により、SecOps は検出およびブロック (防止と応答) のインジケーターの一覧を設定できます。

エンティティの検出、防止、除外を定義するインジケーターを作成します。 実行するアクションと、アクションを適用する期間とその時期、アクションを適用するデバイス グループの範囲を定義できます。

現在サポートされているソースは、Defender for Endpoint のクラウド検出エンジン、自動調査と修復エンジン、エンドポイント防止エンジン (Microsoft Defender ウィルス対策) です。

**クラウド検出エンジン**<br>
Defender for Endpoint のクラウド検出エンジンは、収集されたデータを定期的にスキャンし、設定したインジケーターと一致するものを探します。 一致がある場合、IoC に指定した設定に従ってアクションが実行されます。

**エンドポイント防止エンジン**<br>
インジケーターの同じリストは、防止エージェントによって適用されます。 つまり、Microsoft Defender AV が主な AV 構成である場合、一致したインジケーターは設定に従って処理されます。 たとえば、アクションが "Alert and Block (警告とブロック)" の場合、Microsoft Defender AV によってファイルの実行 (ブロックおよび修復) が防止され、対応する警告が発生します。 一方、アクションが "許可" に設定されている場合、Microsoft Defender AV ではファイルの検出やファイルの実行がブロックされません。

**自動調査と修復エンジン**<BR>
自動調査と修復は同じように動作します。 インジケーターが "許可" に設定されている場合、自動調査と修復では"悪い" 判定は無視されます。 "ブロック" に設定すると、自動調査と修復は、"悪い" として処理します。

> [!NOTE]
> EnableFileHashComputation 設定は、ファイル スキャン時に cert とファイル IoC のファイル ハッシュを計算します。 このポリシーは、信頼できるアプリケーションに属するハッシュと cert の IoC 適用をサポートしています。 ファイル設定の許可またはブロックで、同時に有効化、無効化できます。 EnableFileHashComputation はグループ ポリシーから手動で有効にでき、既定では無効になっています。


現在サポートされているアクションは次のとおりです。
- 許可
- 通知のみ
- 通知とブロック


次のインジケーターを作成できます。
- [ファイル](indicator-file.md)
- [IP アドレス、URL/ドメイン](indicator-ip-domain.md)
- [証明書](indicator-certificates.md)


> [!NOTE]
> 1 テナントあたり 15,000 件のインジケーターの制限があります。 ファイルおよび証明書インジケーターは、[Microsoft Defender ウイルス対策ソフトウェア用に定義された例外](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)をブロックしません。 Microsoft Defender ウイルス対策はパッシブ モードの場合にインジケーターをサポートしません。 


## <a name="related-topics"></a>関連トピック

- [コンテキスト IoC の作成](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [エンドポイント インジケーター API に Microsoft Defender を使用する](ti-indicator.md)
- [パートナー統合ソリューションの使用](partner-applications.md)
