---
title: デバイス名
description: Microsoft Managed Desktop がデバイス名を管理する方法
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: fe29027dab3b3395c14729ee7e04cbe7cebf7261
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317165"
---
# <a name="device-names"></a>デバイス名

Microsoft Managed Desktop では、Windows、Azure Active Directory、およびMicrosoft Intune。

これらのサービスがシームレスに連携するには、デバイスに一貫性のある標準化された名前が必要です。 Microsoft Managed Desktop は、デバイスの登録時に標準化された名前形式 ( `MMD-%RAND11`フォーム) を適用します。 Windowsは、これらの名前を割り当てる必要があります。 自動パイロットの詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ [」を参照してください](../get-started/esp-first-run.md)。

## <a name="automated-name-changes"></a>名前の自動変更

デバイスの名前が後で変更された場合、Microsoft Managed Desktop は自動的に名前を標準化された形式で新しい名前に変更します。 このプロセスは 4 時間ごとに行われます。 名前の変更は、ユーザーが次回デバイスを再起動する際に行います。

> [!IMPORTANT]
> 環境が特定のデバイス名 (たとえば、特定のネットワーク構成をサポートする場合) に依存している場合は、Microsoft Managed Desktop に登録する前に、その依存関係を削除するオプションを調査する必要があります。<br><br>名前の依存関係を維持する必要がある場合は、管理者ポータルから要求を[](../working-with-managed-desktop/admin-support.md)送信して、名前の変更機能を無効にし、目的の名前の形式を使用できます。
