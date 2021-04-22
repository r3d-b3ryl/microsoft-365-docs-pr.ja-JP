---
title: 自動調査を使用して脅威を調査および修復する
description: Microsoft Defender for Endpoint の自動調査フローについて説明します。
keywords: 自動化された、調査、検出、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 5ea869d4016cc794b3046a664c1519f6b3250c67
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933975"
---
# <a name="overview-of-automated-investigations"></a>自動調査の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


どのように動作するのかを確認したいですか? 次のビデオをご覧ください。 <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

自動調査のテクノロジは、さまざまな検査アルゴリズムを使用し、セキュリティ アナリストが使用するプロセスに基づいて行います。 AIR 機能は、アラートを調べ、侵害を解決するために直ちにアクションを実行するように設計されています。 AIR 機能により、アラートの量が大幅に削減され、セキュリティ操作は、より高度な脅威や他の価値の高いイニシアチブに集中できます。 保留中か完了かの修復アクションはすべて、アクション センターで [追跡されます](auto-investigation-action-center.md)。 アクション センターでは、保留中のアクションが承認 (または拒否) され、必要に応じて完了したアクションを元に戻すことができます。

この記事では、AIR の概要を説明し、次の手順と追加のリソースへのリンクを含みます。

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)。

## <a name="how-the-automated-investigation-starts"></a>自動調査の開始方法

自動調査は、アラートがトリガーされた場合、またはセキュリティオペレーターが調査を開始するときに開始できます。

|状況  |結果  |
|---------|---------|
|アラートがトリガーされる     | 一般に、アラートがトリガーされると自動調査[](review-alerts.md)が開始され、インシデント[が](view-incidents-queue.md)作成されます。 たとえば、悪意のあるファイルがデバイスに存在するとします。 そのファイルが検出されると、アラートがトリガーされ、インシデントが作成されます。 自動調査プロセスは、デバイスで開始されます。 他のデバイス上の同じファイルのために他のアラートが生成されると、関連付けられたインシデントと自動調査に追加されます。         |
|調査が手動で開始される     | 自動調査は、セキュリティ運用チームが手動で開始できます。 たとえば、セキュリティオペレーターがデバイスのリストを確認し、デバイスのリスクレベルが高いという通知を行ったとします。 セキュリティオペレーターは、一覧でデバイスを選択してフライアウトを開き、[自動調査の開始] **を選択します**。 |

## <a name="how-an-automated-investigation-expands-its-scope"></a>自動調査によって範囲が拡大される方法

調査の実行中、デバイスから生成された他のアラートは、その調査が完了するまで、継続的な自動調査に追加されます。 さらに、他のデバイスで同じ脅威が見られる場合は、それらのデバイスが調査に追加されます。

特定のエンティティが別のデバイスで見られる場合、自動調査プロセスはスコープを拡大してそのデバイスを含め、そのデバイスで一般的なセキュリティ プレイブックを開始します。 同じエンティティからこの拡張プロセス中に 10 台以上のデバイスが見つかった場合、その展開アクションには承認が必要であり、[保留中のアクション] タブ **に表示** されます。

## <a name="how-threats-are-remediated"></a>脅威の修復方法

アラートがトリガーされ、自動調査が実行されると、調査された証拠ごとに評決が生成されます。 評決は次の場合があります。 
- *悪意のある*;
- *疑わしい*。または 
- *脅威が見つかりません*。 

評決に達すると、自動調査によって 1 つ以上の修復アクションが発生する可能性があります。 修復アクションの例としては、検疫にファイルを送信する、サービスを停止する、スケジュールされたタスクを削除する、などです。 詳細については、「修復アクション [」を参照してください](manage-auto-investigation.md#remediation-actions)。  

組織のオートメーション [セット](automation-levels.md) のレベルや他のセキュリティ設定に応じて、修復アクションは自動的に行われるか、セキュリティ運用チームの承認を得た場合にのみ実行されます。 自動修復に影響を与える可能性のある追加のセキュリティ設定には、望ましくない可能性のあるアプリケーション (PUA) [からの](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) 保護が含まれます。 

保留中か完了かの修復アクションはすべて、アクション センターで [追跡されます](auto-investigation-action-center.md)。 必要に応じて、セキュリティ運用チームは修復アクションを元に戻すことができます。 詳細については、「自動調査後 [の修復アクションの確認と承認」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)。

> [!TIP]
> Microsoft 365 セキュリティ センターの新しい統合調査ページをご覧ください。 詳細については [、「(NEW!)」を参照してください。統合された調査ページ](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。


## <a name="requirements-for-air"></a>AIR の要件

組織には Defender for Endpoint が必要です (「エンドポイント用 Microsoft Defender の最小[要件」を参照)。](minimum-requirements.md)

現在、AIR は次の OS バージョンのみをサポートしています。
- Windows Server 2019
- Windows 10 バージョン 1709 (OS ビルド 16299.1085 [および KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 以降
- Windows 10 バージョン 1803 (OS ビルド 17134.704 [および KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 以降
- Windows 10 バージョン [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) 以降

## <a name="next-steps"></a>次の手順

- [オートメーション レベルの詳細](automation-levels.md)
- [対話型ガイドを参照してください。 Microsoft Defender for Endpoint を使用して脅威を調査して修復する](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Microsoft Defender for Endpoint で自動調査および修復機能を構成する](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>関連項目

- [PUA 保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Microsoft Defender for Office 365 での自動調査と対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Microsoft 365 Defender での自動調査と対応](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
