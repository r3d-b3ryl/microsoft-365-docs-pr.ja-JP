---
title: Microsoft の脅威保護で、空軍の誤検知または誤検知を報告する方法
description: Microsoft の脅威保護で、何らかの問題があるか、またはエアで誤って検出されましたか? 分析のために誤検知または誤検知を Microsoft に送信する方法について説明します。
keywords: 自動化、調査、警告、トリガー、アクション、修復、誤検知、false 負
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d9175e78326832a2be874359babae5ae9c689420
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600084"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査および応答機能の誤検知/ネガを報告する方法

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft の脅威保護ミスの自動化された[調査と応答機能](mtp-autoir.md)を、誤って検出しましたか? Microsoft に報告するか、通知を調整することができます (必要な場合)。 次の表を参考にしてください。 


|アイテム  |検出者  |レポート方法  |
|---------|---------|---------|
|電子メール メッセージ <br/>電子メールの添付ファイル <br/>電子メールメッセージまたは Office ファイルの URL      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[迷惑メールの疑いのあるスパム、フィッシング、Url、およびファイルを Office 365 スキャン用に Microsoft に送信する](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|デバイス上のファイルまたはアプリ    |[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)         |[マルウェア分析のために Microsoft にファイルを提出する](https://www.microsoft.com/wdsi/filesubmission)         |
|正当な使用によってトリガーされるアラート <br/>不正確な警告    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> または <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Cloud App Security ポータルで通知を管理する](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>次のステップ

- [自動調査と対応に関連するアクションを承認または拒否する](mtp-autoir-actions.md)
- [アクション センターの詳細](mtp-action-center.md)
- [Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する](advanced-hunting-overview.md)
