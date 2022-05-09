---
title: グローバル Exchange Online サービスに移行するように MX レコードを更新する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Cloud Germany Exchange Onlineからグローバル Exchange Online サービスに移行する方法について説明します
ms.openlocfilehash: cf11b44ffd8bb52151100e802929d82f5498c668
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192657"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a>グローバル Exchange Online サービスに移行するように MX レコードを更新する

1. Microsoft 365 管理センターにサインインし、**設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a> に移動します。

2. 各ドメインの右側に状態が表示されます。 組織のドメインが Microsoft Cloud Germany Exchange Onlineをポイントしている場合は、MX レコードを更新する必要があります。

3. ドメインをクリックし、 **検出された DNS エラーをクリックし、ここをクリックして表示します**。

4. このページでは、MX レコードを修正する方法について説明します。 ドメインのレジストラーが[ドメイン Connect](../setup/add-domain.md#registrars-with-domain-connect)を使用している場合は、上部にある [レコードの修正] をクリックできます。 それ以外の場合は、ウィザードのリンクに従って、レジストラーの **詳細な手順** に従うことができます。