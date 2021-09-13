---
title: デバイス名
description: デバイスMicrosoft マネージド デスクトップ管理する方法
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218444"
---
# <a name="device-names"></a>デバイス名

Microsoft マネージド デスクトップオートパイロットWindows、Azure Active Directory、およびMicrosoft Intune。 これらのサービスがシームレスに連携するには、デバイスに一貫性のある標準化された名前が必要です。 Microsoft マネージド デスクトップ登録時に、標準化された名前形式 *(MMD-%RAND11* という形式) が適用されます。 WindowsAutopilot は、これらの名前を割り当てる。 自動パイロットの詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](../get-started/esp-first-run.md)。

## <a name="automated-name-changes"></a>名前の自動変更

デバイスの名前が後で変更された場合Microsoft マネージド デスクトップ、デバイスの名前は標準化された形式で新しい名前に自動的に変更されます。 このプロセスは 4 時間ごとに行われます。 名前の変更は、ユーザーが次回デバイスを再起動する際に行います。

> [!IMPORTANT]
> 環境が特定のデバイス名 (たとえば、特定のネットワーク構成をサポートする場合) に依存している場合は、Microsoft マネージド デスクトップ に登録する前に、その依存関係を削除するオプションを調査する必要があります。 名前の依存関係を維持する必要がある場合は、管理者ポータルから要求を[](../working-with-managed-desktop/admin-support.md)送信して、名前の変更機能を無効にし、目的の名前の形式を使用できます。