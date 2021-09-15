---
title: Microsoft Defender for Identity notifications in <DICT__Microsoft⚐365⚐Defender>Microsoft 365 Defender</DICT__Microsoft⚐365⚐Defender>
description: Microsoft Defender for Identity 通知を設定する方法については、Microsoft 365 Defender。
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: dfb3c5e1edbbf77a95a1e1d5888b070a12bfd7a7
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59353624"
---
# <a name="defender-for-identity-notifications-in-microsoft-365-defender"></a>Defender for Identity notifications in Microsoft 365 Defender

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、Microsoft Defender for Identity 通知を[](/microsoft-365/security/defender/overview-security-center)使用する方法について説明[Microsoft 365 Defender。](/defender-for-identity)

> [!IMPORTANT]
> Id ポータルの Defender の場所Microsoft 365 Defender一部のオプションと詳細が変更されました。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細をお読みください。

## <a name="health-issues-notifications"></a>正常性の問題の通知

このMicrosoft 365 Defender、Defender for Identity で正常性の問題に関する電子メール通知の受信者を追加できます。

1. [[Microsoft 365 Defender]](https://security.microsoft.com/)で、[id]**設定** に **移動します**。

    ![[ID] 設定に移動します。](../../media/defender-identity/settings-identities.png)

1. [正常性 **の問題の通知] を選択します**。

1. 受信者のメール アドレスを入力します。 **[追加]** を選択します。

    ![正常性の問題のメール アドレスを入力します。](../../media/defender-identity/health-email-recipient.png)

1. Defender for Identity が正常性の問題を検出すると、受信者は詳細を記載した電子メール通知を受信します。

    ![正常性の問題の電子メールの例。](../../media/defender-identity/health-email.png)

    > [!NOTE]
    > このメールには、問題に関する詳細を示す 2 つのリンクが記載されています。 MDI Health **Center** または **M365D の新しい正常性センターに移動できます**。

## <a name="alert-notifications"></a>アラート通知

このMicrosoft 365 Defender、検出されたアラートの電子メール通知の受信者を追加できます。

1. [[Microsoft 365 Defender]](https://security.microsoft.com/)で、[id]**設定** に **移動します**。

    ![[ID] 設定に移動します。](../../media/defender-identity/settings-identities.png)

1. [アラート **通知] を選択します**。

1. 受信者のメール アドレスを入力します。 **[追加]** を選択します。

    ![検出されたアラートのメール アドレスを入力します。](../../media/defender-identity/alert-email-recipient.png)

## <a name="syslog-notifications"></a>Syslog 通知

Defender for Identity は、指名されたセンサーを介して Syslog サーバーにセキュリティと正常性アラートを送信することで、疑わしいアクティビティを検出した場合に通知できます。

1. [[Microsoft 365 Defender]](https://security.microsoft.com/)で、[id]**設定** に **移動します**。

    ![[ID] 設定に移動します。](../../media/defender-identity/settings-identities.png)

1. [Syslog **通知] を選択します**。

1. syslog 通知を有効にするには、Syslog サービスの **トグルを** オンの位置に **設定** します。

    ![syslog サービスを有効にする。](../../media/defender-identity/syslog-service.png)

1. [サービス **の構成] を選択します**。 ウィンドウが開き、syslog サービスの詳細を入力できます。

    ![syslog サービスの詳細を入力します。](../../media/defender-identity/syslog-sensor.png)

1. 次の詳細を入力します。

    - **センサー** - ドロップダウン リストから、アラートを送信するセンサーを選択します。
    - **サービス エンドポイント** と **ポート** - syslog サーバーの IP アドレスまたは完全修飾ドメイン名 (FQDN) を入力し、ポート番号を指定します。 1 つの Syslog エンドポイントのみを構成できます。
    - **トランスポート** - トランスポート **プロトコル** (TCP または UDP) を選択します。
    - **Format** - 形式 (RFC 3164 または RFC 5424) を選択します。

1. [ **テスト SIEM 通知の送信] を** 選択し、メッセージが Syslog インフラストラクチャ ソリューションで受信されるのを確認します。

1. [**保存**] を選択します。

1. Syslog サービスを構成したら **、Syslog** サーバーに送信する通知の種類 (アラートまたは正常性の問題) を選択できます。

    ![Syslog サービスが構成されています。](../../media/defender-identity/syslog-configured.png)

## <a name="see-also"></a>関連項目

- [Defender for Identity セキュリティアラートの管理](manage-security-alerts.md)
