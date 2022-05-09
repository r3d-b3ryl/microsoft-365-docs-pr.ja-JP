---
title: 自動化ファイルのアップロードを管理する
description: コンテンツ分析を有効にし、分析用に送信されるファイル拡張子と電子メール添付ファイル拡張機能を構成する
keywords: automation, ファイル, アップロード, コンテンツ, 分析, ファイル, 拡張子, 電子メール, 添付ファイル
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21e7eb17759ff6127f3d91137023c058abe2715e
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166136"
---
# <a name="manage-automation-file-uploads"></a>自動化ファイルのアップロードを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

コンテンツ分析機能を有効にして、特定のファイルと電子メールの添付ファイルを自動的にクラウドにアップロードして、自動調査で追加の検査を行えるようにします。

ファイル拡張子名と電子メール添付ファイル拡張子名を指定して、ファイルと電子メールの添付ファイルを識別します。

たとえば、ファイルまたは添付ファイルの拡張子名として *exe* と *bat* を追加すると、これらの拡張機能を含むすべてのファイルまたは添付ファイルが自動的にクラウドに送信され、自動調査中に追加検査が行われます。

## <a name="add-file-extension-names-and-attachment-extension-names"></a>ファイル拡張子名と添付ファイル拡張子名を追加します。

1. ナビゲーション ウィンドウで、[**Endpoints** \> **Rules** \> **Automation のアップロード****設定**\>] を選択します。

2. コンテンツ分析の設定をオンと **オフ** の間 **で** 切り替えます。

3. 次の拡張機能名と個別の拡張機能名をコンマで構成します。
   - **ファイル拡張子名** - 電子メールの添付ファイルを除く疑わしいファイルは、追加の検査のために送信されます

## <a name="related-topics"></a>関連項目

- [自動化フォルダーの除外を管理する](manage-automation-folder-exclusions.md)
