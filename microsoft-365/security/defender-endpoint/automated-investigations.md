---
title: 自動調査を使用して脅威を調査および修復する
description: Microsoft Defender for Endpointの自動調査フローについて理解します。
keywords: 自動化, 調査, 検出, Microsoft Defender for Endpoint
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.date: 11/24/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: eadf9fe7f6112d1219f085662686b2a930b3ff28
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789802"
---
# <a name="overview-of-automated-investigations"></a>自動調査の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

動作を確認しますか? 次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

自動調査のテクノロジは、さまざまな検査アルゴリズムを使用し、セキュリティ アナリストが使用するプロセスに基づいています。 AIR 機能は、アラートを調査し、侵害を解決するための直ちにアクションを実行するように設計されています。 AIR 機能により、アラートの量が大幅に削減され、セキュリティ運用は、より高度な脅威やその他の価値の高いイニシアチブに集中できます。 保留中でも完了でも、すべての修復アクションは [、アクション センター](auto-investigation-action-center.md)で追跡されます。 アクション センターでは、保留中のアクションが承認 (または拒否) され、必要に応じて完了したアクションを元に戻すことができます。

この記事では、AIR の概要を説明し、次の手順と追加のリソースへのリンクを含みます。

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automated-investigations-abovefoldlink)

## <a name="how-the-automated-investigation-starts"></a>自動調査の開始方法

自動調査は、アラートがトリガーされたとき、またはセキュリティオペレーターが調査を開始したときに開始できます。

<br>

****

|状況|動作|
|---|---|
|アラートがトリガーされる|一般に、自動調査は [、アラート](review-alerts.md) がトリガーされ、 [インシデント](view-incidents-queue.md) が作成されたときに開始されます。 たとえば、悪意のあるファイルがデバイスに存在するとします。 そのファイルが検出されると、アラートがトリガーされ、インシデントが作成されます。 自動調査プロセスは、デバイスで開始されます。 他のデバイス上の同じファイルが原因で他のアラートが生成されるため、関連するインシデントと自動調査に追加されます。|
|調査が手動で開始される|セキュリティ運用チームは、自動調査を手動で開始できます。 たとえば、セキュリティオペレーターがデバイスの一覧を確認していて、デバイスのリスク レベルが高いことを確認するとします。 セキュリティ オペレーターは、一覧でデバイスを選択してそのポップアップを開き、[ **自動調査の開始**] を選択できます。|
|

## <a name="how-an-automated-investigation-expands-its-scope"></a>自動調査によってその範囲が拡大する方法

調査の実行中、デバイスから生成されたその他のアラートは、その調査が完了するまで、継続的な自動調査に追加されます。 さらに、他のデバイスで同じ脅威が見られる場合は、それらのデバイスが調査に追加されます。

別のデバイスで犯罪エンティティが見られる場合、自動調査プロセスによってそのデバイスが含まれる範囲が拡大され、そのデバイスで一般的なセキュリティ プレイブックが開始されます。 この拡張プロセス中に同じエンティティから 10 台以上のデバイスが見つかった場合、その拡張アクションには承認が必要であり、[保留中の **アクション** ] タブに表示されます。

## <a name="how-threats-are-remediated"></a>脅威の修復方法

アラートがトリガーされ、自動調査が実行されると、調査された証拠ごとに判定が生成されます。 判定には次のものがあります。

- *悪意のあるも* の。
- *疑わしい*;または
- *脅威は見つかりませんでした*。

判定に達すると、自動調査によって 1 つ以上の修復アクションが発生する可能性があります。 修復アクションの例としては、ファイルの検疫への送信、サービスの停止、スケジュールされたタスクの削除などがあります。 詳細については、「 [修復アクション」を](manage-auto-investigation.md#remediation-actions)参照してください。

組織の自動化セット [のレベル](automation-levels.md) 、および他のセキュリティ設定に応じて、修復アクションは自動的に行われるか、セキュリティ運用チームの承認を得た場合にのみ行うことができます。 自動修復に影響を与える可能性のある追加のセキュリティ設定には、 [望ましくない可能性があるアプリケーション](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA) からの保護が含まれます。

保留中でも完了でも、すべての修復アクションは [、アクション センター](auto-investigation-action-center.md)で追跡されます。 必要に応じて、セキュリティ運用チームは修復アクションを元に戻すことができます。 詳細については、 [自動調査後の修復アクションの確認と承認に関するページを](/microsoft-365/security/defender-endpoint/manage-auto-investigation)参照してください。

> [!TIP]
> Microsoft 365 Defender ポータルの新しい統合調査ページを確認します。 詳細については、 [(NEW!) を参照してください。統合調査ページ](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。

## <a name="requirements-for-air"></a>AIR の要件

組織には Defender for Endpoint が必要です ([「Microsoft Defender for Endpointの最小要件](minimum-requirements.md)」を参照)。

> [!NOTE]
> 調査と応答を自動化するには、パッシブ モードまたはアクティブ モードで実行するためのMicrosoft Defender ウイルス対策が必要です。 Microsoft Defender ウイルス対策が無効またはアンインストールされている場合、自動調査と応答は正しく機能しません。

現時点では、AIR では次の OS バージョンのみがサポートされています。

- Windows Server 2012 R2 (プレビュー)
- Windows Server 2016 (プレビュー)
- Windows Server 2019
- Windows Server 2022
- Windows 10バージョン 1709 (OS ビルド 16299.1085 と [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 以降
- Windows 10バージョン 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 以降
- Windows 10バージョン [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) 以降
- Windows 11

## <a name="next-steps"></a>次の手順

- [オートメーション レベルの詳細を確認する](automation-levels.md)
- [対話型ガイドを参照してください:Microsoft Defender for Endpointを使用して脅威を調査して修復する](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Microsoft Defender for Endpointで自動調査と修復機能を構成する](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>関連項目

- [PUA 保護](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Microsoft Defender for Office 365での自動調査と対応](/microsoft-365/security/office-365-security/office-365-air)
- [Microsoft 365 Defender での自動調査と応答](/microsoft-365/security/defender/m365d-autoir)
