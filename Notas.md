## Notas de AWS Associated

<details><summary> 10. Arquitectura & Diseño
</summary>

### AWS Cloud Disaster Recovery Scenarios

The AWS Cloud offers a range of disaster recovery (DR) approaches, providing quick and reliable recovery options for IT systems. These scenarios are arranged based on the speed at which a system can be available to users after a disaster event:

1. **Backup and Restore**
   - Simple and cost-effective approach.
   - Back up data and applications to the AWS Cloud for recovery.
   - No use of conventional tape backups.
   - Amazon EC2 instances are utilized for testing as needed.
   - Low storage costs with Amazon S3 (as low as $0.015/GB for infrequent access).

2. **Pilot Light**
   - Analogy from gas heating: a small flame ignites the entire furnace quickly.
   - Replicate a portion of your IT structure for core services.
   - AWS Cloud takes over seamlessly during a disaster.
   - Critical core elements must already be configured and running in AWS.
   - Rapidly provision a full-scale production environment around the critical core during recovery.

3. **Warm Standby**
   - A scaled-down version of a fully functional environment is always running in the cloud.
   - Extends the pilot light approach and decreases recovery time.
   - Some services are always running, improving readiness for recovery.
   - Identify and fully duplicate business-critical systems on AWS.

4. **Multi-site**
   - Run on AWS and existing on-site infrastructure in an active-active configuration.
   - Data replication method determined by Recovery Time Objective or Recovery Point Objective.
   - Ensures continuous operations with minimal downtime or data loss during the DR process.

Each of these scenarios provides flexible and efficient options for businesses to protect their critical data and applications, ensuring seamless recovery from disasters anytime, anywhere. For more information on each approach, refer to the respective links provided.

Fuente
[AWS](https://aws.amazon.com/blogs/publicsector/rapidly-recover-mission-critical-systems-in-a-disaster/)

</details>
