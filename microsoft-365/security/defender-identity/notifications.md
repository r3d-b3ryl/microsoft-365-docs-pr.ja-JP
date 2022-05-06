---
title: Microsoft 365 Defenderで通知をMicrosoft Defender for Identityする
description: Microsoft 365 DefenderでMicrosoft Defender for Identity通知を設定する方法について説明します。
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: 89ed7ae50bf89c28bde81ea02e8905d0056ede53
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470925"
---
# <a name="defender-for-identity-notifications-in-microsoft-365-defender"></a>Microsoft 365 Defenderの Defender for Identity 通知

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、[Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center)で[Microsoft Defender for Identity](/defender-for-identity)通知を操作する方法について説明します。

> [!IMPORTANT]
> Microsoft 365 Defenderとの統合の一環として、一部のオプションと詳細は Defender for Identity ポータルの場所から変更されています。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細を参照してください。

## <a name="health-issues-notifications"></a>正常性の問題の通知

Microsoft 365 Defenderでは、Defender for Identity の正常性の問題に関する電子メール通知の受信者を追加できます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で、[**設定**] に移動し、[**ID] に移動します**。

  :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="列名の [ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::


1. **[正常性の問題の通知**] を選択します。

1. 受信者のメール アドレスを入力します。 **[追加]** を選択します。

   :::image type="content" source="../../media/defender-identity/health-email-recipient.png" alt-text="[正常性の問題の通知] サブメニュー項目" lightbox="../../media/defender-identity/health-email-recipient.png":::

1. Defender for Identity が正常性の問題を検出すると、受信者は詳細を含む電子メール通知を受け取ります。

   :::image type="content" source="../../media/defender-identity/health-email.png" alt-text="正常性の問題の電子メール" lightbox="../../media/defender-identity/health-email.png":::

    > [!NOTE]
    > この電子メールには、問題の詳細を示す 2 つのリンクが用意されています。 **MDI ヘルス センター** または **M365D の新しいヘルス センターに** 移動できます。

## <a name="alert-notifications"></a>アラート通知

Microsoft 365 Defenderでは、検出されたアラートの電子メール通知の受信者を追加できます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で、[**設定**] に移動し、[**ID] に移動します**。

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::

1. [ **アラート通知**] を選択します。

1. 受信者のメール アドレスを入力します。 **[追加]** を選択します。

   :::image type="content" source="../../media/defender-identity/alert-email-recipient.png" alt-text="アラート通知サブメニュー項目" lightbox="../../media/defender-identity/alert-email-recipient.png":::

## <a name="syslog-notifications"></a>Syslog 通知

Defender for Identity は、指定されたセンサーを介して Syslog サーバーにセキュリティと正常性のアラートを送信することで、疑わしいアクティビティが検出されたときに通知できます。

> [!NOTE]
> Defender for Identity と Microsoft Sentinel を統合する方法については、Microsoft Sentinel [との統合Microsoft 365 Defender](/azure/sentinel/microsoft-365-defender-sentinel-integration)参照してください。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で、[**設定**] に移動し、[**ID] に移動します**。

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[名前] 列の [ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::

1. **[Syslog 通知]** を選択します。

1. syslog 通知を有効にするには、 **Syslog サービス** のトグルをオンの位置 **に** 設定します。

   :::image type="content" source="../../media/defender-identity/syslog-service.png" alt-text="オンにできる Syslog サービス オプション" lightbox="../../media/defender-identity/syslog-service.png":::

1. [ **サービスの構成] を選択します**。 ウィンドウが開き、syslog サービスの詳細を入力できます。

   :::image type="content" source="../../media/defender-identity/syslog-sensor.png" alt-text="Syslog サービスの詳細を入力するページ" lightbox="../../media/defender-identity/syslog-sensor.png":::

1. 次の詳細を入力します:

    - **センサー** - ドロップダウン リストから、アラートを送信するセンサーを選択します。
    - **サービス エンドポイント** と **ポート** - syslog サーバーの IP アドレスまたは完全修飾ドメイン名 (FQDN) を入力し、ポート番号を指定します。 構成できる Syslog エンドポイントは 1 つだけです。
    - **トランスポート** - **トランスポート** プロトコル (TCP または UDP) を選択します。
    - **形式** - 形式 (RFC 3164 または RFC 5424) を選択します。

1. [ **テスト SIEM 通知の送信** ] を選択し、Syslog インフラストラクチャ ソリューションでメッセージが受信されたことを確認します。

1. **[保存]** を選択します。

1. **Syslog サービス** を構成したら、Syslog サーバーに送信する通知の種類 (アラートまたは正常性の問題) を選択できます。

   :::image type="content" source="../../media/defender-identity/syslog-configured.png" alt-text="Syslog サービスが構成されているオプションがオンになっている" lightbox="../../media/defender-identity/syslog-configured.png":::

## <a name="see-also"></a>関連項目

- [Defender for Identity セキュリティ アラートを管理する](manage-security-alerts.md)
